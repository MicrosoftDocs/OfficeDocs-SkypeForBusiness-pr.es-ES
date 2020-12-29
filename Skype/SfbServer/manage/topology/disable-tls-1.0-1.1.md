---
title: Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Prepare e implemente la deshabilitación de TLS 1,0 y 1,1 en sus entornos.'
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734298"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015

El propósito de este artículo es proporcionar las instrucciones necesarias para preparar e implementar la deshabilitación de TLS 1,0 y 1,1 en los entornos. Este proceso requiere una amplia planeación y preparación. Revise atentamente toda la información de este artículo a medida que realiza el plan para deshabilitar TLS 1,0 y 1,1 para su organización. Tenga en cuenta que hay muchas dependencias externas y condiciones de conectividad que podrían verse afectadas por la deshabilitación de TLS 1.0/1.1, por lo que la planeación y las pruebas exhaustivas están garantizadas.

## <a name="in-this-article"></a>En este artículo

- [Fondo y ámbito](#background)
- [Requisitos previos y proceso](#prerequisites-and-process)
- [Escenarios de implementación avanzada](#advanced-deployment-scenarios)

## <a name="background"></a>Información previa

Los controladores principales para proporcionar TLS 1,0 y 1,1 deshabilitar la compatibilidad con Skype empresarial Server local son el Consejo de estándares de seguridad de la industria de la tarjeta de pago (PCI) y los estándares federales de procesamiento de información. Puede encontrar más información sobre los requisitos de PCI [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft no puede proporcionar instrucciones sobre si su organización debe o no cumplir con estos u otros requisitos. Debe determinar si es necesario para deshabilitar TLS 1,0 o 1,1 en sus entornos.

Microsoft ha creado una nota del producto sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)y también se recomienda la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Ámbito de compatibilidad

El *ámbito* se refiere a los límites de compatibilidad. *Totalmente probadas y admitidas* significa que hemos admitido completamente y probado la deshabilitación de TLS 1,0 y 1,1 para las versiones de producto indicadas. *Actualmente investigado* significa eso; Estamos investigando activamente la introducción de estos productos en el ámbito de la compatibilidad con la deshabilitación de TLS. *Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1,0 o 1,1 y no funcionarán, con las excepciones indicadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores completamente probados y admitidos

- Skype empresarial Server 2019 CU1 17.0.2046.123 (2019 de junio) o superior
- Skype empresarial Server 2015 CU9 6.0.9319.548 (May 2019) o posterior en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o reemplazando la actualización), 2012 R2 o 2016.
- Actualización local de Skype empresarial Server 2015 con CU9 6.0.9319.548 (May 2019) o posterior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o reemplazando la actualización) o 2012 R2.
- Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o superior, guía [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Aplicación de sucursal con funciones de supervivencia (SBA) con Skype empresarial Server 2015 CU6 HF2 o superior (confirme con el proveedor que ha embalado las actualizaciones adecuadas y que se han puesto a disposición para su dispositivo)
- Servidor de sucursal con funciones de supervivencia (SBS) con Skype empresarial Server 2015 CU6 HF2 o superior
- Lync Server 2013 **solo rol perimetral**, esto se debe a que el rol perimetral no tiene una dependencia en Windows fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Clientes completamente probados y admitidos

- Cliente de escritorio de Lync 2013 (Skype empresarial), MSI y C2R, incluido el [15.0.5023.1000 básico o superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Cliente de escritorio de Skype empresarial 2016, MSI [16.0.4678.1000 o superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluido Basic
- Skype empresarial 2016 hacer clic para ejecutar requiere las actualizaciones de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Mensual y Semi-Annual destino, 16 \. 0 \. 9126 \. 2152 o superior
    - Semi-Annual y canal diferido, 16 \. 0 \. 8431 \. 2242 o superior
- Skype empresarial en Mac 16,15 o superior
- Skype empresarial para iOS y Android 6,19 o superior
- Salones de Microsoft Teams (anteriormente conocido como sistema de salas de Skype v2 SRS V2) 4.0.64.0 (2018 de diciembre) o superior
- Actualización de Surface hub para Team Edition basada en KB4499162 (mayo 2019, OS compilación 15063,1835) o superior
- Skype Web App 2015 CU6 HF2 o superior (incluye el servidor)

### <a name="currently-being-investigated"></a>Actualmente investigando

- Panel de calidad de llamadas (nueva instalación después de que se hayan deshabilitado los 1,1 TLS 1,0, vea a continuación) *
 
### <a name="out-of-scope"></a>Fuera de ámbito

Excepto donde se indique, los siguientes productos no se encuentran en el ámbito de la compatibilidad con TLS 1.0/1.1 deshabilitar y no funcionarán en un entorno en el que se hayan deshabilitado TLS 1,0 y 1,1. Esto significa que: Si todavía utiliza servidores o clientes fuera del ámbito, debe actualizarlos o quitarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de su implementación local de Skype empresarial Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 o inferior
- Lync para Mac 2011
- Lync 2013 para Mobile-iOS, iPad, Android o Windows Phone
- Cliente de la tienda Windows "MX" de Lync
- Sistema Lync Room (también conocido como SRSv1). LRS ha alcanzado el final del soporte técnico el 9 de octubre de 2018 y no se actualizará para admitir TLS 1,2.
- Todos los clientes de Lync 2010
- Lync Phone Edition: Guía actualizada [aquí](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Aplicación de sucursal con funciones de supervivencia basada en 2013 (SBA) o servidor de sucursal con funciones de supervivencia (SBS)
- Cloud Connector Edition (CCE)
- Skype empresarial para Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 toma una dependencia en Windows fabric versión 1,0.  En la fase de diseño de Lync Server 2013, se escogió Windows fabric 1,0 por su nueva arquitectura distribuida y convincente para proporcionar replicación, alta disponibilidad y tolerancia a errores.  Con el tiempo, tanto Skype empresarial Server como Windows fabric han mejorado enormemente esta arquitectura conjunta con rediseño significativo en versiones posteriores.  El servidor actual de Skype empresarial 2015 usa Windows fabric 3,0, por ejemplo.

Por desgracia, Windows fabric 1,0 **no admite TLS 1,2.  Sin embargo, se actualizará Lync Server 2013 para trabajar con TLS 1,2**. Esto estará disponible en la próxima actualización acumulativa de Lync Server 2013.  Proporcionamos compatibilidad con TLS 1,2 para habilitar los escenarios de coexistencia, migración, Federación y híbrido.

Si su organización debe deshabilitar TLS 1,0 y 1,1, y usa actualmente Lync Server 2013, le recomendamos que comience el proceso de planeación, con la posibilidad de que tenga que realizar una actualización local o una migración en paralelo (nuevos grupos, mover usuarios) a Skype empresarial Server 2015 o superior.  O bien, puede que quiera acelerar la migración a Skype empresarial online.

#### <a name="call-quality-dashboard"></a>Panel de calidad de llamadas

El panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1,0 durante la nueva instalación (la primera vez que se instala en los entornos locales).  Actualmente estamos investigando este problema y planea liberar una corrección en un futuro próximo.  Si tiene previsto instalar el CQD y deshabilitar también TLS 1,0, se recomienda completar primero la instalación del CQD y, a continuación, continuar con la deshabilitación de TLS 1,0.

#### <a name="skype-for-business-sdn-manager"></a>Skype empresarial SDN Manager

Skype empresarial SDN Manager con SQL una base de datos tiene una dependencia en TLS 1,0 durante la nueva instalación. Si tiene previsto instalar Skype empresarial SDN Manager con SQL a base de datos y deshabilitar también TLS 1,0, le recomendamos que complete primero Skype for Business SDN Manager y continúe con la deshabilitación de TLS 1,0. En caso de que TLS 1,0 se haya deshabilitado antes de la instalación, debe habilitar TLS 1,0 temporalmente en el servidor back-end de SQL Server que se usará para hospedar la base de datos SQL de SDN Manager de Skype empresarial.

#### <a name="third-party-devices"></a>Dispositivos de otros fabricantes

En dispositivos de terceros, como teléfonos 3PIP, conferencias de vídeo, proxies inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1,2, realice pruebas minuciosamente y póngase en contacto con el proveedor si es necesario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Consideraciones sobre la Federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales

Debe planear cuidadosamente y considerar el impacto de la deshabilitación de TLS 1.0/1.1 en los servidores perimetrales.  Una vez que se han deshabilitado los TLS 1,0 y 1,1, es posible que otras organizaciones ya no puedan federarse a su organización.

Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con versiones anteriores con sistemas externos no revisados (SfB 2015, Lync 2013) o anteriores (2010).

Microsoft no puede proporcionar consejos o recomendaciones sobre si la red perimetral (o cualquier red) cae en el estándar PCI; que debe determinar la empresa individual.

Skype empresarial online es compatible con TLS 1,2 en la actualidad, por lo que no se espera ningún impacto en Hybrid/Federation con online.

PIC (conectividad de mensajería instantánea pública) para el servicio de consumidor de Skype: no esperamos que la deshabilitación de TLS 1.0/1.1 afecte a la [conectividad de Skype](../../deploy/deploy-skype-connectivity.md); Las puertas de enlace de Microsoft PIC ya admiten TLS 1,2.

## <a name="prerequisites-and-process"></a>Requisitos previos y proceso

Excepto cuando se haya indicado anteriormente, una 1,1 1,0 vez que se hayan deshabilitado los servidores fuera de ámbito, los clientes y dispositivos podrán funcionar correctamente, o en todo caso. Esto puede significar que debe pausar y esperar una guía actualizada de Microsoft. Una vez que esté seguro de que cumple todos los requisitos y tiene un plan para abordar las brechas, continúe.

En un nivel alto, mientras Skype empresarial Server 2019 está preparado para el procedimiento en la instalación, Skype empresarial Server 2015 requerirá la instalación de CU9, la aplicación de actualizaciones de requisitos previos a .NET y SQL, la implementación de claves de registro de requisitos previos y, por último, la ronda de actualizaciones de configuración del sistema operativo (por ejemplo, la deshabilitación de TLS 1,0 y 1,1 Es muy importante que complete la instalación de todos los requisitos previos, incluido Skype for Business Server 2015 CU6 HF2, antes de deshabilitar TLS 1,0 y 1,1 en cualquier servidor del entorno. Todos los servidores de Skype empresarial, incluidos el rol perimetral y los extremos de SQL, requieren las actualizaciones. Asegúrese también de que todos los clientes compatibles (en el ámbito) se han actualizado a las versiones mínimas necesarias. No olvide actualizar también las estaciones de trabajo de administración.

Queremos seguir el orden habitual de las operaciones de "Inside Out" para actualizar servidores de Skype empresarial. Trate los grupos de directores, el chat persistente y los grupos emparejados de la misma manera que lo haría normalmente. El orden y los métodos para la actualización se tratan [aquí](topology.md) y [aquí](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Proceso de alto nivel

1. Pruebe todos los pasos del laboratorio antes de configurar los servidores de producción.
2. Realice una copia de seguridad y conserve una copia del registro exportado en todos y cada uno de los servidores individuales que se van a actualizar. No puede compartir registros entre servidores; contienen claves únicas basadas en el equipo.
3. Actualice todos los servidores de Skype empresarial 2015 a CU9 o superior. Para Skype empresarial Server 2019, actualice a CU1 o versiones posteriores.
4. Instale todos los requisitos previos en todos los servidores.
5. Implementar claves de registro de requisitos previos.
6. Asegúrese de que se actualizan todos los clientes del ámbito.
7. Deshabilite TLS 1,0 y 1,1 a través de importación de registro.
8. Validar que las cargas de trabajo funcionan como se esperaba.
    - Si se detectan problemas, la solución de problemas y la resolución o
    - Restaure el registro desde el paso 2 para volver a habilitar TLS 1,0 y 1,1
9. Valide que solo se use TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Instalar los requisitos previos para todos los servidores

La actualización de dependencias exhaustivas es necesaria antes de empezar a deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo en las implementaciones de Skype empresarial Server 2015. Las siguientes son las versiones mínimas que pueden admitir TLS 1,2. Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype empresarial Server del entorno antes de empezar a deshabilitar TLS 1,0 y 1,1.

- Skype empresarial Server 2015 CU9 6.0.9319.548 (mayo 2019) o posterior
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o superior con valor schusestrongcrypto habilitado en el registro (proporcionado a continuación)
- SQL debe actualizarse en todos los servidores y servidores de la 2015 de Skype empresarial. Actualice primero el SQL del grupo de servidores Enterprise Edition, y luego sus respectivos FEs. 
    - [SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o superior/sql server 2012 SP2 + CU16 o superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)o superior/SQL Server 2014 SP2
     - [SQL Server Native Client para SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Controlador ODBC 11 de Microsoft para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o superior
     - [Objetos de administración compartidos para SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes para SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Pasos básicos para instalar los requisitos previos, en el orden recomendado de operaciones

1. Instale la actualización de CU9 de Skype empresarial Server en todos los servidores. 
    1. Instale la actualización de los componentes que usan el actualizador.
    2. Actualice las bases de datos de acuerdo con procedimientos documentados. Para Skype empresarial Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Validar la funcionalidad del producto en la implementación antes de seguir adelante con otros cambios.
2. Descargue el instalador sin conexión de .NET 4,7. 
    1. Referencias [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.
    3. Referencias [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (edición estándar): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Ejecute el paquete de instalación.
    7. Reinicie el servidor.
3. Actualice SQL Express 2014 en todos los servidores. 
    1. Referencias [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Descargar SQL 2014 SP2 
        - Referencias [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copie los medios de instalación en una carpeta del servidor (ej: C:\ 01_2014SqlSp2)
    4. Asegurarse de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end 
        - Ex (edición estándar): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Abrir un símbolo del sistema de administración y actualizar todos los componentes e instancias instalados 
        - Ejemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/Action = patch/AllInstances
4. Actualice SQL Native Client. 
    1. Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Descargar desde [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end. 
        - Ex (edición estándar): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Detener la ejecución de las instancias de SQL instaladas 
        - Precio ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Precio ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (sólo en Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Instale el paquete.
5. Actualice ODBC driver 11 for SQL Server para que incluya compatibilidad con TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Descargue [ODBC driver 11 for SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.
        - Ejemplo (Standard Edition): ```Stop-CsWindowsService```
        - Ejemplo (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Instale el paquete.
6. Implementar claves de registro de requisitos previos.

### <a name="pre-requisite-registry-keys"></a>Claves del registro de requisitos previos

Copie y pegue la siguiente prueba en el Bloc de notas y cambie el nombre a TLSPreReq. reg o un nombre de su elección y, a continuación, importe:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Para los back-end de SQL para los grupos de servidores Enterprise Edition, los requisitos previos y la deshabilitación de TLS deben tratarse como actualizaciones de SQL o del sistema operativo; Consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Aunque se pueden combinar los pasos de la aplicación de requisitos previos y TLS, recomendamos que se apliquen todos los requisitos previos antes de deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo. El enfoque de los procedimientos recomendados sería preparar el entorno mediante la implementación de todos los requisitos previos, validando que las cargas de trabajo funcionan correctamente y según lo esperado y, a continuación, deshabilitar la deshabilitación de TLS 1.0/1.1 en un momento posterior.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deshabilitar TLS 1,0 y 1,1 a través de importación de registro

Antes de continuar con los pasos siguientes, asegúrese de *haber completado todos los requisitos previos y los servidores actualizados de Skype empresarial*.

Copie el siguiente texto en un archivo del Bloc de notas y cambie el nombre a **TLSDisable. reg**:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importe el archivo. reg en cada servidor en el que desee deshabilitar TLS 1,0 y 1,1. Reinicie el servidor. Una vez que los servicios vuelvan a estar en línea, pase al siguiente servidor. El enfoque para los grupos de servidores Enterprise Edition es el mismo que se realizaría para cualquier actualización del sistema operativo.

Es posible que haya observado que estamos haciendo algo más que simplemente deshabilitar la TLS 1,0 y la 1,1 aquí. Estamos admitiendo el reordenamiento del conjunto de cifrado (como se mostró anteriormente) y la deshabilitación de algunos de los cifrados débiles más antiguos. Esta es la primera vez que hemos admitido oficialmente estos cambios en SCHANNEL y Crypto API en Skype empresarial Server, y es importante tener en cuenta que estos cambios son los únicos admitidos y que se han probado en este momento. Es posible que considere configuraciones adicionales en el futuro, pero por ahora, no modifique el archivo de importación de registro en la implementación.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que las cargas de trabajo funcionan según lo esperado

Una vez que se hayan deshabilitado los TLS 1,0 y 1,1 en el entorno, asegúrese de que todas las cargas de trabajo principales funcionan como se esperaba, como la mensajería instantánea & presencia, las llamadas P2P, la telefonía IP empresarial, etc.

**Validar que solo se use TLS 1,2**

Haga que el equipo de seguridad realice una nueva auditoría del tráfico de Skype empresarial para asegurarse de que los protocolos antiguos TLS 1,0 y 1,1 ya no se usan.

Como alternativa, puede usar Internet Explorer para probar las conexiones TLS a los servicios web desde Skype empresarial Server 2015 después de que se hayan deshabilitado TLS 1,0 y TLS 1,1.

1. Inicie Internet Explorer.
2. Seleccione **herramientas**  >  **Opciones de Internet**.
3. Seleccione la pestaña **avanzadas** .
4. En **configuración**, desplácese hasta la parte inferior.
5. Compruebe que están habilitados TLS 1,0, TLS 1,1 y TLS 1,2.
6. Examine la dirección URL del servicio Web interno del grupo de SfB 2015 (debe conectarse correctamente).
7. Vuelva a Internet Explorer y deshabilite la opción para **usar TLS 1,2** solamente.
8. Explore la dirección URL del servicio Web interno del grupo de SfB 2015 de nuevo (debe producirse un error de conexión).

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Escenarios de implementación avanzada

Debido a que algunos requisitos previos de dependencia son necesarios para admitir TLS 1,2 en Skype empresarial Server 2015, la instalación desde medios de RTM producirá un error en cualquier sistema en el que se hayan deshabilitado TLS 1,0 y 1,1.

**Implementar nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que se hayan deshabilitado TLS 1,0 y 1,1 en su entorno.**

**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los archivos binarios de SQL actualizados en un CU posterior y se actualizará este artículo en el futuro.

**Opción 2:** Preinstalar instancias locales de SQL (RTCLOCAL y LYNCLOCAL)

1. Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64.exe) en la carpeta local en FE. Supongamos que la ruta de acceso a la carpeta <SQL_FOLDER_PATH>.
2. Inicie PowerShell o el símbolo del sistema y vaya a <SQL_FOLDER_PATH>.
3. Para crear la instancia de SQL de RTCLOCAL, ejecute el siguiente comando. Espere hasta que finalice SQLEXPR_x64.exe antes de continuar:

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = autoautomati
1. Para crear la instancia de SQL de LYNCLOCAL, ejecute el siguiente comando. Espere hasta que finalice SQLEXPR_x64.exe antes de continuar con el paso siguiente:

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = "autom? ticamente
1. Ejecute el programa de instalación de Skype empresarial Server 2015 RTM.
2. Siga los pasos restantes de la sección requisitos previos anterior.

**Opción 3:** También puede reemplazar manualmente los archivos binarios en un directorio de medios de instalación local de la siguiente manera:

1. [Instalación de requisitos previos de Skype empresarial Server](../../deploy/install/install-prerequisites.md)  
2. Instale .NET 4,7: 
      - **Nota:** Primero presentamos compatibilidad para .NET 4,7 en Skype empresarial Server 2015 CU5 (6.0.9319.281). Por lo tanto, en los pasos posteriores que se indican a continuación, actualizaremos los componentes principales antes de la instalación principal.
      - Descargar: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referencia: [software que debe instalarse antes de una implementación de Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiar archivos o carpetas ISO: 
    - Con la ISO adjunta de Skype empresarial Server 2015, abra el directorio raíz de la unidad en la que se ha adjuntado como (ej: D: \) en el explorador de archivos.
    - Copie todas las carpetas y los archivos en una carpeta de un disco local (por ejemplo: C:\SkypeForBusiness2015ISO).
    - **Nota:** Antes de instalar componentes, será necesario actualizar algunos archivos para admitir TLS 1,2.
4. Reemplazar paquetes MSI/EXE: 
    - Reemplace los paquetes MSI y EXE existentes en la carpeta/SETUP/AMD64/de los medios de instalación en el equipo local.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Cambie el nombre a SQLEXPR_x64 en el equipo local y reemplace el archivo existente en la carpeta SETUP/AMD64/de los medios de instalación.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Nota:** Cambie el nombre si es necesario para sqlncli.msi y, a continuación, reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
    - Objetos de administración de SQL: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccione esta selección para descargar sólo SharedManagementObjects.msi.
        - **Nota:** Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
    - Tipos de SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccionar para descargar sólo CQLSysClrTypes.msi
        - **Nota**: Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
5. Instale los componentes principales: 
    - Ejecute Setup.exe desde la carpeta SETUP/AMD64/de los medios de instalación. Siga las instrucciones para instalar los componentes principales
    - Cierre los componentes principales.
6. Actualizar componentes principales: 
    - Descargue el instalador de la actualización de Skype empresarial.
    - Ejecute el instalador para actualizar los componentes principales e instalar los contadores de rendimiento.
    - **Nota:** A partir de la versión de CU6HF2, la característica de actualización automática solo se instala actualmente hasta CU6. Por lo tanto, el actualizador debe ejecutarse por separado para actualizar los componentes principales a 6.0.9319.516.
    - Referencias https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar herramientas administrativas (opcional): 
    - Se instalarán Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) y Microsoft System CLR Types for SQL Server 2014 (x64) con los archivos actualizados. Además, el generador de topologías y el panel de control de Skype empresarial Server 2015 estarán disponibles en la máquina local.
8. Instale el almacén de configuración local (paso 1): 
     - Abra el Asistente para la implementación, haga clic en instalar o actualizar el sistema de Skype empresarial Server y, a continuación, haga clic en **Ejecutar** en el paso 1: instalar el almacén de configuración local.
     - Haga clic en **siguiente** en el cuadro de diálogo **instalar almacén de configuración local** .
     ![Cuadro de diálogo instalar el almacén de configuración local](../../media/local-configuration-store.png)
     - Revise los resultados y asegúrese de que el estado de la tarea es completada. Revise el archivo de registro resultante; para ello, haga clic en **Ver registro**.
     ![El estado de la tarea muestra como completado](../../media/local-configuration-task-completed.png)
     - Haga clic en **Finalizar**.
9. Configurar o quitar componentes de Skype empresarial Server (paso 2):
    - Abra el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server** y, a continuación, haga clic en **Ejecutar** en el paso 2: configurar o quitar componentes de Skype empresarial Server
    - Haga clic en **siguiente** en el cuadro de diálogo Configurar componentes de Skype empresarial Server.
    ![la ventana Configurar componentes de Skype empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Revise el registro mediante Ver registro y compruebe que la instalación se ha completado sin problemas. 
    - Haga clic en **Finalizar**.
10. Continúe con la instalación y la configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).
