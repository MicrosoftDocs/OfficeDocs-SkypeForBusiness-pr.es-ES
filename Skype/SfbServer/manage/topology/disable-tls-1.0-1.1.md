---
title: Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Prepare e implemente la deshabilitación de TLS 1,0 y 1,1 en sus entornos.'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "34275244"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015

El propósito de este artículo es proporcionar la orientación necesaria para preparar e implementar la deshabilitación de TLS 1,0 y 1,1 en sus entornos. Este proceso requiere una extensa planificación y preparación. Revise atentamente toda la información de este artículo a medida que realiza su plan para deshabilitar TLS 1,0 y 1,1 para su organización. Tenga en cuenta que existen muchas dependencias externas y condiciones de conectividad que pueden verse afectadas por la deshabilitación de TLS 1.0/1.1 para garantizar una planificación y pruebas amplias.

## <a name="in-this-article"></a>En este artículo

- [Fondo y ámbito](#background)
- [Requisitos previos y proceso](#prerequisites-and-process)
- [Escenarios de implementación avanzada](#advanced-deployment-scenarios)

## <a name="background"></a>Información general

Los drivers principales para proporcionar TLS 1,0 y 1,1 deshabilitar el soporte para Skype empresarial Server local son los requisitos del Consejo de estándares de seguridad de la industria de las tarjetas de pago (PCI) y los estándares federales de procesamiento de información. Puede encontrar más información sobre los requisitos de PCI [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft no puede proporcionar instrucciones sobre si su organización debe cumplir con estos u otros requisitos. Debe determinar si es necesario para deshabilitar TLS 1,0 o 1,1 en sus entornos.

Microsoft ha creado un documento sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), y también recomendamos la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Ámbito de compatibilidad

El *ámbito* se refiere a los límites de compatibilidad. En el caso de Skype empresarial Server local, *en el ámbito* significa que hemos admitido completamente la deshabilitación de las versiones de los productos de TLS 1,0 y 1,1. *Actualmente investigado* significa eso; Estamos investigando de forma activa el alcance de estos productos para la compatibilidad con la desactivación de TLS. *Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1,0 o 1,1 y no funcionarán, con las excepciones indicadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente probados y admitidos

- Skype Empresarial Server 2019
- Skype empresarial Server 2015 CU6 HF2 6.0.9319.516 ([actualización de marzo de 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) y versiones posteriores en: 
    - Windows Server 2012 (con KB 3140245 o actualización reemplazada), 2012 R2 o 2016
- Actualización local de Skype empresarial Server 2015, con CU6 HF2 y versiones posteriores en 
    - Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización que reemplaza) o 2012 R2
- Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o versiones posteriores, guía [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Dispositivo de rama superviviente (SBA) con Skype empresarial Server 2015 CU6 HF2 o superior (confirme con su proveedor que han embalado las actualizaciones de Appropiate y que están disponibles para su dispositivo)
- Servidor de sucursal (SBS) superviviente con Skype empresarial Server 2015 CU6 HF2 o versiones posteriores
- **Solo rol de Edge**de Lync Server 2013, esto se debe a que el rol de Edge no tiene una dependencia en Windows fabric 1,0.


### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente probados y admitidos

- Cliente de escritorio de Lync 2013 (Skype empresarial), MSI y C2R, que incluye Basic [15.0.5023.1000 y versiones posteriores](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Cliente de escritorio de Skype empresarial 2016, MSI [16.0.4678.1000 y superior](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluido básico
- Skype empresarial 2016 hacer clic para ejecutarse requiere las actualizaciones de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Con objetivo mensual y semianual, 16\.0\.9126\.2152 y superiores
    - Canal semianual y diferido, 16\.0\.8431\.2242 y superiores
- Skype empresarial en Mac 16,15 y versiones posteriores
- Skype empresarial para iOS y Android 6,19 y versiones posteriores
- Skype Web App 2015 CU6 HF2 y versiones posteriores (se suministra con el servidor)

### <a name="currently-being-investigated"></a>Investigando en este momento

#### <a name="devices"></a>Dispositivos

- Sistema de sala de Lync (también conocido como SRSv1)
- Salas de Microsoft Teams
- Surface Hub
- Equipo de sucursal basado en 2015 (SBA) o servidor de sucursal superviviente (SBS)

#### <a name="other"></a>Otros

- Panel de calidad de llamadas (nueva instalación después de que se haya deshabilitado TLS 1,0, 1,1, consulte a continuación) *
 
### <a name="out-of-scope"></a>Fuera del ámbito

Excepto donde se indique lo contrario, los siguientes productos no están en el ámbito de TLS 1.0/1.1 deshabilitar el soporte técnico y no funcionarán en un entorno en el que se hayan deshabilitado TLS 1,0 y 1,1.  Qué significa: Si aún usa clientes o servidores fuera del ámbito, debe actualizarlos o eliminarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de su implementación local de Skype empresarial Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 y versiones anteriores
- Lync para Mac 2011
- Lync 2013 para móvil: iOS, iPad, Android o Windows Phone
- Cliente de la tienda Windows "MX" de Lync
- Todos los clientes de Lync 2010
- Lync Phone Edition: Guía actualizada [aquí](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Equipo de sucursal basado en 2013 (SBA) o servidor de sucursal superviviente (SBS)
- Cloud Connector Edition (CCE)
- Skype Empresarial para Windows Phone

### <a name="exceptions"></a>Excepciones

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 toma una dependencia en Windows fabric versión 1,0.  En la fase de diseño de Lync Server 2013, se escogió Windows fabric 1,0 para su nueva arquitectura distribuida y atractiva para proporcionar replicación, alta disponibilidad y tolerancia a errores.  Con el tiempo, tanto Skype empresarial Server como Windows fabric han mejorado enormemente esta arquitectura conjunta con un rediseño significativo en versiones posteriores.  El servidor actual de Skype empresarial 2015 usa Windows fabric 3,0, por ejemplo.

Lamentablemente, Windows fabric 1,0 **no es compatible con TLS 1,2.  Sin embargo, actualizaremos Lync Server 2013 para que funcione con TLS 1,2**. Esto estará disponible en la siguiente actualización acumulativa para Lync Server 2013.  Proporcionamos compatibilidad con TLS 1,2 para habilitar escenarios de coexistencia, migración, Federación y híbrida.

Si su organización tiene que deshabilitar TLS 1,0 y 1,1 y actualmente usa Lync Server 2013, le recomendamos que comience su proceso de planeación, con la posibilidad de que tenga que realizar una actualización local o una migración en paralelo (nuevos grupos, mover usuarios) a Skype para Business Server 2015 o superior.  O bien, es posible que desee acelerar la migración a Skype empresarial online.

#### <a name="call-quality-dashboard"></a>Panel de calidad de llamadas

El panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1,0 durante la nueva instalación (la primera vez que se instala en entornos locales).  Actualmente estamos investigando este problema y tenemos previsto publicar una corrección en un futuro próximo.  Si tiene previsto instalar el CQD y también deshabilitar TLS 1,0, le recomendamos que complete primero la instalación del CQD y, a continuación, continúe con la desactivación de TLS 1,0.

#### <a name="third-party-devices"></a>Dispositivos de terceros

En dispositivos de terceros, como teléfonos 3PIP, videoconferencias, proxies inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1,2, realizar pruebas con cuidado y póngase en contacto con el proveedor si es necesario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Consideraciones sobre la Federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales

Debe planificar cuidadosamente y considerar el impacto de la deshabilitación de TLS 1.0/1.1 en los servidores perimetrales.  Una vez que TLS 1,0 y 1,1 estén deshabilitados, es posible que vea que otras organizaciones ya no pueden federarse con su organización.

Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con los sistemas externos no revisados (SfB 2015, Lync 2013) o versiones anteriores (2010).

Microsoft no puede proporcionar asesoramiento ni recomendaciones sobre si su red perimetral (o cualquier red) está bajo el estándar PCI; que debe determinar la empresa individual.

Skype empresarial online es capaz de TLS 1,2 hoy, así que no se espera ninguna repercusión en la híbrida o la Federación con conexión.

PIC (conectividad de mensajería instantánea pública) para el servicio de consumidores de Skype: no esperamos que la deshabilitación de TLS 1.0/1.1 afecte a la [conectividad de Skype](../../deploy/deploy-skype-connectivity.md); Las puertas de enlace de Microsoft PIC ya son compatibles con TLS 1,2.

## <a name="prerequisites-and-process"></a>Requisitos previos y proceso

Excepto cuando se indique lo mencionado anteriormente, una vez que los servidores TLS 1,0 y 1,1 estén deshabilitados fuera de ámbito, los clientes y dispositivos dejarán de funcionar correctamente o en todo momento. Esto puede significar que debes pausar y esperar la orientación actualizada de Microsoft. Una vez que esté satisfecho con todos los requisitos y tenga un plan para abordar las brechas, continúe.

En un nivel alto, mientras que Skype empresarial Server 2019 está listo para el procedimiento de instalación, Skype empresarial Server 2015 requerirá la instalación de CU6 HF2, la aplicación de actualizaciones de requisitos previos a .NET y SQL, la implementación de claves de registro de requisitos previos y, por último, una el redondeo de las actualizaciones de configuración del sistema operativo (es decir, deshabilitar TLS 1,0 y 1,1 a través de la importación de archivos de registro). Es muy importante que complete la instalación de todos los requisitos previos, incluyendo Skype empresarial Server 2015 CU6 HF2, antes de deshabilitar TLS 1,0 y 1,1 en cualquier servidor de su entorno. Todos los servidores de Skype empresarial, incluidos el rol perimetral y los extremos SQL, requieren las actualizaciones. Asegúrese también de que todos los clientes compatibles (dentro del ámbito) se hayan actualizado a las versiones mínimas necesarias. No se olvide de actualizar también las estaciones de trabajo de administración.

Queremos seguir el orden habitual de las operaciones de "Inside Out" para actualizar los servidores de Skype empresarial. Tratar los pools de directores, los chats persistentes y los grupos emparejados de la misma manera que lo haría normalmente. El orden y los métodos de actualización se tratan [aquí](topology.md) y [aquí](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Proceso de alto nivel

1. Pruebe todos los pasos de su laboratorio antes de configurar los servidores de producción.
2. Realice una copia de seguridad y conserve una copia del registro exportado en cada servidor individual que se va a actualizar. No puede compartir registros entre servidores; contienen claves únicas basadas en el equipo.
3. Actualice todos los servidores de Skype empresarial 2015 a CU6 HF2 o versiones posteriores. (Para Skype empresarial Server 2019, no se necesita CU)
4. Instale todos los requisitos previos para todos los servidores.
5. Implementar claves de registro de requisitos previos.
6. Asegúrese de que se actualizan todos los clientes dentro del ámbito.
7. Deshabilite TLS 1,0 y 1,1 a través de importación de registro.
8. Valide que las cargas de trabajo funcionen según lo esperado.
    - Si se producen problemas, solucionar problemas y resolverlos, o bien
    - Restaurar el registro del paso 2 para volver a habilitar TLS 1,0 y 1,1
9. Valide que solo se use TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Instalar los requisitos previos para todos los servidores

Es necesario actualizar las dependencias extensas antes de empezar a deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo en las implementaciones de Skype empresarial Server 2015. A continuación se muestran las versiones mínimas que pueden admitir TLS 1,2. Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype empresarial en su entorno antes de deshabilitar TLS 1,0 y 1,1.

- Skype empresarial Server 2015 CU6 HF2 6.0.9319.516 ([actualización 2018 de marzo](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) o superior
- [.NET Framework 4,7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) o superior con SchUseStrongCrypto habilitado en el registro (proporcionado a continuación)
- SQL debe actualizarse en todos los servidores y servidores de la versión 2015 de Skype empresarial. Actualice en primer lugar SQL del grupo de servidores Enterprise Edition y luego sus respectivos FEs. 
    - SQL Server 2014 SP1 + CU5 ([Link](https://support.microsoft.com/help/3130926)) o superior/sql server 2012 SP2 + CU16 o superior/sql server 2014 RTM + CU12 ([Link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) o superior/SQL Server 2014 SP2
    - SQL Server Native Client para SQL Server 2012 ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Microsoft ODBC driver 11 for SQL Server ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) o superior
    - Objetos de administración compartida para SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes para SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Pasos básicos para instalar requisitos previos, en el orden recomendado de operaciones

1. Instale la actualización de Skype empresarial Server CU6HF2 (6.0.9319.516) en todos los servidores. 
    1. Instale la actualización de los componentes con el actualizador.
    2. Actualice las bases de datos de acuerdo con procedimientos documentados. Las instrucciones se documentan en [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Validar la funcionalidad del producto en la implementación antes de continuar con cualquier otro cambio.
2. Descargue el instalador sin conexión de .NET 4,7. 
    1. Reference[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.
    3. Reference[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (edición estándar): Stop-CsWindowsServices
    5. Ex (edición empresarial): Invoke-CsComputerFailover
    6. Ejecute el paquete de instalación.
    7. Reinicie el servidor.
3. Actualice SQL Express 2014 en todos los servidores. 
    1. Reference[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Descargar SQL 2014 SP2 
        - Reference[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Copie los medios de instalación a una carpeta en el servidor (p. ej.: C:\01_2014SqlSp2)
    4. Asegurarse de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end 
        - Ex (edición estándar): Stop-CsWindowsService
        - Ex (edición empresarial): Invoke-CsComputerFailove
    5. Abrir un símbolo del sistema de administrador y actualizar todos los componentes e instancias instalados 
        - Ejemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/Action = patch/AllInstances
4. Actualice SQL Native Client. 
    1. Referencia: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Descargar de[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end. 
        - Ex (edición estándar): Stop-CsWindowsServices
        - Ex (edición empresarial): Invoke-CsComputerFailove
    4. Detener la ejecución de las instancias de SQL instaladas 
        - Por ejemplo: get-Service ' MSSQL $ RTCLOCAL ' | Detener: servicio
        - Por ejemplo: get-Service ' MSSQL $ LYNCLOCAL ' | Detener: servicio
        - Ex (solo en Standard Edition): get-Service ' MSSQL $ RTC ' | Detener: servicio
    5. Instale la actualización.
5. Actualice el controlador de ODBC 11 para SQL Server. 
    1. Referencia: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Descargar de[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Asegurarse de que los servicios de Skype empresarial Server 2015 estén detenidos en el servidor front-end 
        - Ex (edición estándar): Stop-CsWindowsService
        - Ex (edición empresarial): Invoke-CsComputerFailove
    4. Instale la actualización.
6. Implementar claves de registro de requisitos previos.

### <a name="pre-requisite-registry-keys"></a>Claves de registro de requisitos previos

Copie/pegue la prueba siguiente en el Bloc de notas y cambie el nombre a TLSPreReq. reg o un nombre de su elección, a continuación, importe:

```
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

Para los back-end de SQL para los grupos de Enterprise Edition, los requisitos previos y la desactivación de TLS deberían tratarse como cualquier otra actualización de SQL o OS; Consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Aunque se pueden combinar los pasos de la aplicación previa y la deshabilitación de TLS, recomendamos encarecidamente que se apliquen todos los requisitos previos antes de deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo. El enfoque más práctico sería preparar el entorno mediante la implementación de todos los requisitos previos, la validación de que todas las cargas de trabajo funcionan correctamente y de la manera esperada, y, a continuación, deshabilitar la desactivación de TLS 1.0/1.1 más adelante.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deshabilitar TLS 1,0 y 1,1 a través de importación de registro

Antes de continuar con los pasos siguientes, asegúrese de *que ha completado todos los requisitos previos y los servidores actualizados de Skype empresarial*.

Copie el texto siguiente en un archivo del Bloc de notas y cambie el nombre a **TLSDisable. reg**:

```
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

Importe el archivo. reg en cada servidor en el que desee deshabilitar TLS 1,0 y 1,1. Reinicie el servidor. Una vez que los servicios se vuelvan a conectar, pasa al siguiente servidor. El enfoque para los grupos de Enterprise Edition es el mismo que haría para cualquier actualización del sistema operativo.

Es posible que haya observado que estamos haciendo algo más que simplemente deshabilitar TLS 1,0 y 1,1 aquí. Hemos admitido el reorden de conjuntos de cifrado (como se muestra arriba) y la desactivación de algunos cifrados débiles más antiguos. Esta es la primera vez que hemos admitido oficialmente estos cambios en SCHANNEL y Crypto API en Skype empresarial Server, y es importante tener en cuenta que estos cambios son los únicos que admitimos y que hemos probado en este momento. Es posible que consideres configuraciones adicionales en el futuro, pero por ahora, no modifiques el archivo de importación de registro en la implementación.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que las cargas de trabajo funcionen según lo esperado

Una vez que TLS 1,0 y 1,1 se hayan deshabilitado en su entorno, asegúrese de que todas las cargas de trabajo principales funcionen de la manera esperada, como la mensajería instantánea & presencia, las llamadas P2P, la telefonía IP empresarial, etc.

**Validar que solo se use TLS 1,2**

Haga que su equipo de seguridad realice una nueva auditoría del tráfico de Skype empresarial para asegurarse de que los protocolos antiguos TLS 1,0 y 1,1 ya no se usan.

Como alternativa, puede usar Internet Explorer para probar las conexiones TLS con los servicios Web de Skype empresarial Server 2015 después de que se haya deshabilitado TLS 1,0 y TLS 1,1.

1. Inicie Internet Explorer.
2. Seleccione **herramientas** > **Opciones de Internet**.
3. Seleccione la pestaña **avanzadas** .
4. En **configuración**, desplácese hasta la parte inferior.
5. Compruebe que las TLS 1,0, TLS 1,1 y TLS 1,2 estén habilitadas.
6. Examine la dirección URL del servicio Web interno del grupo de SfB 2015 (debe conectarse correctamente).
7. Vuelva a Internet Explorer y deshabilite la opción para **usar TLS 1,2** solo.
8. Vuelva a examinar la dirección URL del servicio Web interno de su grupo de SfB 2015 (no se puede conectar).

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Escenarios de implementación avanzada

Debido a que se necesitan algunos requisitos previos de dependencia para admitir TLS 1,2 en Skype empresarial para 2015, la instalación desde medios de RTM fallará en cualquier sistema donde se hayan deshabilitado TLS 1,0 y 1,1.

**Implementar nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que se hayan deshabilitado TLS 1,0 y 1,1 en su entorno.**

**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los binarios de SQL actualizados en una CU futura, y Actualizaremos este artículo en el futuro.

**Opción 2:** Anteriores a la instalación de instancias locales de SQL (RTCLOCAL y LYNCLOCAL)

1. Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64. exe) en la carpeta local de FE. Supongamos que la ruta de la carpeta <SQL_FOLDER_PATH>.
2. Inicie PowerShell o símbolo del sistema y vaya a <SQL_FOLDER_PATH>.
3. Para crear la instancia de SQL RTCLOCAL, ejecute el siguiente comando. Espere hasta que finalice SQLEXPR_x64. exe antes de continuar:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administradores "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = autoautomatizacióni
1. Para crear la instancia de SQL LYNCLOCAL, ejecute el siguiente comando. Espere hasta que finalice SQLEXPR_x64. exe antes de continuar con el siguiente paso:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administradores "/BROWSERSVCSTARTUPTYPE =" automático "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = automático
1. Ejecute el programa de instalación de Skype empresarial Server 2015 RTM.
2. Siga los pasos restantes de la sección requisitos previos anterior.

**Opción 3:** También puede reemplazar manualmente los binarios en un directorio de medios de instalación local de la siguiente manera:

1. [Instalar los requisitos previos de Skype empresarial Server](../../deploy/install/install-prerequisites.md)  
2. 2. Instale .NET 4,7: 
      - **Nota:** En primer lugar, hemos introducido compatibilidad con .NET 4,7 en Skype empresarial Server 2015 CU5 + (6.0.9319.281). Por lo tanto, en los pasos posteriores siguientes actualizaremos los componentes principales antes de la instalación principal.
      - Descargar: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Referencia: [software que debe instalarse antes de una implementación de Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiar archivos o carpetas ISO: 
    - Con la conexión ISO de Skype empresarial Server 2015, abra el directorio raíz de la unidad a la que se ha adjuntado (\) por ejemplo: D: en el explorador de archivos.
    - Copie todas las carpetas y archivos en una carpeta de un disco local (p. ej.: C:\SkypeForBusiness2015ISO).
    - **Nota:** Antes de instalar componentes, será necesario actualizar algunos archivos para admitir TLS 1,2.
4. Reemplazar paquetes MSI/EXE: 
    - Sustituya los paquetes MSI y EXE existentes en la carpeta/SETUP/AMD64/de los medios de instalación de la máquina local.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Cambie el nombre a SQLEXPR_x64 en la máquina local y reemplace el archivo existente en la carpeta SETUP/AMD64/de los medios de instalación.
    - Cliente SQL Native:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Nota:** Cambie el nombre si es necesario a SQLNCLI. msi y, a continuación, reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
    - Objetos de administración de SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccione esta para descargar solo SharedManagementObjects. msi.
        - **Nota:** Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
    - Tipos de SQL CLR:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccione para descargar solo CQLSysClrTypes. msi.
        - **Nota**: Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.
5. Instalar componentes básicos: 
    - Ejecute setup. exe desde la carpeta SETUP/AMD64/de los medios de instalación. Siga las instrucciones para instalar los componentes principales
    - Cierre los componentes principales.
6. Actualizar componentes básicos: 
    - Descargar el instalador de actualización de Skype empresarial.
    - Ejecute el instalador para actualizar los componentes principales e instale los contadores de rendimiento.
    - **Nota:** A partir de la versión de CU6HF2, la característica de actualización automática solo se instalará actualmente hasta CU6. Por lo tanto, el actualizador debe ejecutarse por separado para actualizar los componentes principales a 6.0.9319.516.
    - Referencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar herramientas administrativas (opcional): 
    - Esto instalará el cliente nativo de Microsoft SQL Server 2012, los objetos de administración de SQL Server 2014 (x64) y los tipos CLR del sistema de Microsoft para SQL Server 2014 (x64) con los archivos actualizados. Además, el generador de topología y el panel de control de Skype empresarial Server 2015 estarán disponibles en la máquina local.
8. Instalar el almacén de configuración local (paso 1): 
     - Abra el Asistente para la implementación, haga clic en instalar o actualizar el sistema de Skype empresarial Server y haga clic en **Ejecutar** en el paso 1: instalar el almacén de configuración local.
     - Haga clic en **siguiente** en el cuadro de diálogo **instalar el almacén de configuración local** .
     ![Cuadro de diálogo instalar el almacén de configuración local](../../media/local-configuration-store.png)
     - Revise los resultados y asegúrese de que el estado de la tarea es completada. Revise el archivo de registro resultante haciendo clic en **Ver registro**.
     ![El estado de la tarea muestra completado](../../media/local-configuration-task-completed.png)
     - Haga clic en **Finalizar**.
9. Instalar o quitar componentes de Skype empresarial Server (paso 2):
    - Abra el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y haga clic en **Ejecutar** en el paso 2: configurar o quitar los componentes de Skype empresarial Server.
    - Haga clic en **siguiente** en el cuadro de diálogo Configurar componentes de Skype empresarial Server.
    ![la ventana Configurar componentes de Skype empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Revise el registro con Ver registro y valide que la configuración se haya completado sin problemas. 
    - Haga clic en **Finalizar**.
10. Continúe con la instalación y la configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).
