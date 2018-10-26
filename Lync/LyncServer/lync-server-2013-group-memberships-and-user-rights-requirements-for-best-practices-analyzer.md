---
title: "Requisitos pertenencias a grupo y derechos usuario del Analizador de proceds. recom."
TOCTitle: "Appart. à des gr. et conf. req. des droits d'ut. pour Best Practices Analyzer"
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48277241
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de pertenencias a grupo y de derechos de usuario para el Analizador de procedimientos recomendados

 

_**Última modificación del tema:** 2012-10-21_

Para ejecutar correctamente el Analizador de procedimientos recomendados, la cuenta de usuario que utilice para iniciar sesión debe ser miembro del grupo de administradores en el equipo local. Además, para examinar el entorno, la cuenta de usuario debe ser miembro de los siguientes grupos:

  - **Admins. del dominio**   Para listar la información de los servicios de dominio de Active Directory y llamar a los proveedores de Instrumental de administración de Windows (WMI) en los controladores de dominio y los servidores de catálogos globales.

  - **Administradores**   Necesarios en cada equipo interno de Lync Server 2013 y en cada servidor perimetral para llamar a los proveedores de Instrumental de administración de Windows (WMI) y obtener acceso al registro.

  - **RTCUniversalReadOnlyAdmins**   Derechos administrativos en Lync Server 2013 totales o delegados de solo lectura.

  - **Exchange View Only Administrator**   Administrador de Exchange completo o delegado de solo ver en la organización Microsoft Exchange.

Si su cuenta de usuario no posee los derechos de usuario suficientes, tiene dos opciones:

  - En el símbolo del sistema, use el comando **runas** para ejecutar la herramienta con una cuenta que no posee derechos de usuario suficientes. La sintaxis es la siguiente:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - En la página **Conectar con Active Directory**, escriba las credenciales de las cuentas que planea utilizar para ejecutar el Analizador de procedimientos recomendados. Haga clic en **Mostrar opciones de conexión avanzadas**. Puede especificar tres cuentas: una para conectar con los servicios de dominio de Active Directory, otra para conectar con Lync Server 2013Servidores perimetrales y la última para conectar con los servidores de Exchange. Si no especifica ninguna de estas cuentas, se emplea la cuenta de usuario utilizada para iniciar sesión y ejecutar el Analizador de procedimientos recomendados.

