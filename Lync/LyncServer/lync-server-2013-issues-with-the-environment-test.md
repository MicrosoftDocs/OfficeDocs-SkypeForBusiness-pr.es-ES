---
title: Problemas con la prueba de entorno
TOCTitle: Problemas con la prueba de entorno
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48277299
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problemas con la prueba de entorno

 

_**Última modificación del tema:** 2012-09-21_

El Analizador de procedimientos recomendados ofrece una forma de verificar que la configuración del entorno de Lync Server 2013 es compatible. Durante la comprobación de los servicios de dominio de Active Directory, el Analizador de procedimientos recomendados realiza las siguientes operaciones:

  - Verifica la preparación del bosque y el esquema de Servicios de dominio de Active Directory.

  - Identifica el número de sitios y dominios de Servicios de dominio de Active Directory en la implementación.

  - Comprueba el bosque y los niveles de dominio.

  - Comprueba la versión del controlador del dominio.

  - Identifica el contexto de denominación del dominio, la configuración y el esquema.

  - Identifica el número de usuarios habilitados.

  - Comprueba el lugar de almacenamiento de la configuración de los Servicios de dominio de Active Directory.

  - Comprueba los puertos de conexión de servicio (SCP) de Lync Server.

  - Identifica la versión de la base de datos.

## Resolución de problemas del entorno

Si durante la prueba del entorno se detectan problemas, probablemente se deban a problemas de configuración de Active Directory o el nivel de software que se ejecuta en determinados servidores. Por ejemplo, si el Analizador de procedimientos recomendados detecta que algún controlador de dominio del entorno ejecuta Windows Server 2000, emitirá una advertencia y será necesario actualizar esos controladores de dominio a una versión compatible de Windows Server.

