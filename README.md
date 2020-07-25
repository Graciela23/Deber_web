# Deber_web

CREATE DATABASE IF NOT EXISTS `deberweb` /*!40100 DEFAULT CHARACTER SET latin1 */;
USE `deberweb`;

-- Volcando estructura para tabla deberweb.grupo
CREATE TABLE IF NOT EXISTS `grupo` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `descripcion` varchar(50) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=latin1;

-- La exportación de datos fue deseleccionada.

-- Volcando estructura para tabla deberweb.plancuenta
CREATE TABLE IF NOT EXISTS `plancuenta` (
  `id_PC` int(11) NOT NULL AUTO_INCREMENT,
  `codigo` varchar(50) NOT NULL DEFAULT '0',
  `grupo` int(11) NOT NULL DEFAULT 0,
  `descripcion` varchar(50) NOT NULL DEFAULT '0',
  `naturaleza` varchar(50) NOT NULL DEFAULT '0',
  `estado` tinyint(1) NOT NULL DEFAULT 0,
  PRIMARY KEY (`id_PC`),
  KEY `FK_plancuenta_grupo` (`grupo`),
  CONSTRAINT `FK_plancuenta_grupo` FOREIGN KEY (`grupo`) REFERENCES `grupo` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=latin1;