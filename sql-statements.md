### Create Tables

```sql
-- MySQL Script generated by MySQL Workbench
-- Thu Mar 11 23:46:09 2021
-- Model: New Model    Version: 1.0
-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema psionic_storm
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema psionic_storm
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `psionic_storm` DEFAULT CHARACTER SET utf8 ;
-- -----------------------------------------------------
-- Schema psionic_storm
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema psionic_storm
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `psionic_storm` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
USE `psionic_storm` ;

-- -----------------------------------------------------
-- Table `psionic_storm`.`user`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`user` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`user` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `login_id` VARCHAR(45) NOT NULL,
  `nickname` VARCHAR(45) NOT NULL,
  `hashed_password` VARCHAR(200) NOT NULL,
  `salt` VARCHAR(200) NOT NULL,
  `created_at` DATETIME NOT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB
AUTO_INCREMENT = 32
DEFAULT CHARACTER SET = utf8mb4
COLLATE = utf8mb4_unicode_ci;


-- -----------------------------------------------------
-- Table `psionic_storm`.`space`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`space` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`space` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `created_at` DATETIME NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`id`),
  INDEX `fk_space_user_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_space_user`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`salon`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`salon` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`salon` (
  `id` INT NOT NULL,
  `created_at` DATETIME NOT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`book`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`book` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`book` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(200) NOT NULL,
  `author` VARCHAR(200) NOT NULL,
  `description` VARCHAR(2000) NOT NULL,
  `created_at` DATETIME NOT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`book_has_space`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`book_has_space` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`book_has_space` (
  `book_id` INT NOT NULL,
  `space_id` INT NOT NULL,
  PRIMARY KEY (`book_id`, `space_id`),
  INDEX `fk_book_has_space_space1_idx` (`space_id` ASC) VISIBLE,
  INDEX `fk_book_has_space_book1_idx` (`book_id` ASC) VISIBLE,
  CONSTRAINT `fk_book_has_space_book1`
    FOREIGN KEY (`book_id`)
    REFERENCES `psionic_storm`.`book` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_book_has_space_space1`
    FOREIGN KEY (`space_id`)
    REFERENCES `psionic_storm`.`space` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`book_has_salon`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`book_has_salon` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`book_has_salon` (
  `book_id` INT NOT NULL,
  `salon_id` INT NOT NULL,
  PRIMARY KEY (`book_id`, `salon_id`),
  INDEX `fk_book_has_salon_salon1_idx` (`salon_id` ASC) VISIBLE,
  INDEX `fk_book_has_salon_book1_idx` (`book_id` ASC) VISIBLE,
  CONSTRAINT `fk_book_has_salon_book1`
    FOREIGN KEY (`book_id`)
    REFERENCES `psionic_storm`.`book` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_book_has_salon_salon1`
    FOREIGN KEY (`salon_id`)
    REFERENCES `psionic_storm`.`salon` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`review`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`review` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`review` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `title` TEXT(2000) NOT NULL,
  `content` INT NOT NULL,
  `created_at` DATETIME NOT NULL,
  `updated_at` DATETIME NOT NULL,
  `book_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`id`, `book_id`),
  INDEX `fk_review_book1_idx` (`book_id` ASC) VISIBLE,
  INDEX `fk_review_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_review_book1`
    FOREIGN KEY (`book_id`)
    REFERENCES `psionic_storm`.`book` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_review_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`quote`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`quote` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`quote` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `content` VARCHAR(2000) NOT NULL,
  `created_at` DATETIME NOT NULL,
  `updated_at` DATETIME NOT NULL,
  `book_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`id`, `book_id`, `user_id`),
  INDEX `fk_quote_book1_idx` (`book_id` ASC) VISIBLE,
  INDEX `fk_quote_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_quote_book1`
    FOREIGN KEY (`book_id`)
    REFERENCES `psionic_storm`.`book` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_quote_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`review_comment`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`review_comment` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`review_comment` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `comment` VARCHAR(2000) NOT NULL,
  `created_at` DATETIME NOT NULL,
  `updated_at` DATETIME NOT NULL,
  `review_id` INT NOT NULL,
  `review_book_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`id`, `review_id`, `review_book_id`),
  INDEX `fk_review_comment_review1_idx` (`review_id` ASC, `review_book_id` ASC) VISIBLE,
  INDEX `fk_review_comment_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_review_comment_review1`
    FOREIGN KEY (`review_id` , `review_book_id`)
    REFERENCES `psionic_storm`.`review` (`id` , `book_id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_review_comment_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`quote_comment`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`quote_comment` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`quote_comment` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `comment` VARCHAR(2000) NOT NULL,
  `created_at` DATETIME NOT NULL,
  `updated_at` DATETIME NOT NULL,
  `quote_id` INT NOT NULL,
  `quote_book_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`id`, `quote_id`, `quote_book_id`, `user_id`),
  INDEX `fk_quote_comment_quote1_idx` (`quote_id` ASC, `quote_book_id` ASC) VISIBLE,
  INDEX `fk_quote_comment_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_quote_comment_quote1`
    FOREIGN KEY (`quote_id` , `quote_book_id`)
    REFERENCES `psionic_storm`.`quote` (`id` , `book_id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_quote_comment_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `psionic_storm`.`salon_has_user`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `psionic_storm`.`salon_has_user` ;

CREATE TABLE IF NOT EXISTS `psionic_storm`.`salon_has_user` (
  `salon_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`salon_id`, `user_id`),
  INDEX `fk_salon_has_user_user1_idx` (`user_id` ASC) VISIBLE,
  INDEX `fk_salon_has_user_salon1_idx` (`salon_id` ASC) VISIBLE,
  CONSTRAINT `fk_salon_has_user_salon1`
    FOREIGN KEY (`salon_id`)
    REFERENCES `psionic_storm`.`salon` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_salon_has_user_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `psionic_storm`.`user` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;

USE `psionic_storm` ;

SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;

```