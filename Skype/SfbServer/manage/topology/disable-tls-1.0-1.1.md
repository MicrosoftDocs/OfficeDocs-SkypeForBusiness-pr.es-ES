---
title: Deshabilitar TLS 1.0/1.1 en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Preparar e implementar la deshabilitación de TLS 1.0 y 1.1 en los entornos.
ms.openlocfilehash: 214605f80c79d7ecb334aeca49d29210e888b511
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726401"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deshabilitar TLS 1.0/1.1 en Skype Empresarial Server 2015

Este artículo le ayuda a preparar e implementar la deshabilitación de TLS 1.0 y 1.1 en sus entornos. Este proceso requiere una amplia planeación y preparación. Revise detenidamente toda la información de este artículo mientras planea deshabilitar TLS 1.0 y 1.1 para su organización. Existen muchas dependencias externas y condiciones de conectividad que podrían afectarse al deshabilitar TLS 1.0/1.1, por lo que se requiere una planeación y pruebas exhaustivas.

- [Fondo y ámbito](#background-and-scope)
- [Requisitos previos y proceso](#prerequisites-and-process)
- [Escenarios de implementación avanzada](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Fondo y ámbito

Los controladores principales para proporcionar TLS 1.0 y 1.1 deshabilitan la compatibilidad con Skype Empresarial Server local son los requisitos del Consejo de estándares de seguridad de la industria de tarjetas de pago (PCI) y los estándares federales de procesamiento de información. Encontrará más información sobre los requisitos pci [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft no puede proporcionar instrucciones sobre si su organización está obligada a cumplir estos u otros requisitos. Debe determinar si es necesario deshabilitar TLS 1.0 o 1.1 en sus entornos.

Microsoft ha producido una white paper sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)y también se recomienda la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Ámbito de compatibilidad

*El ámbito* hace referencia a los límites de compatibilidad. *Totalmente probado y compatible significa* que se admite totalmente y se ha probado la deshabilitación de TLS 1.0 y 1.1 para las versiones de producto enumeradas. *Actualmente se está investigando* significa justo eso; estamos investigando activamente la posibilidad de que estos productos entren en el ámbito de la compatibilidad con la deshabilitación tls. *Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1.0 o 1.1 y no funcionarán, con excepciones observadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente probados y compatibles

- Skype Empresarial Server 2019 CU1 17.0.2046.123 (junio de 2019) o posterior
- Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o posterior en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización de superseding), 2012 R2 o 2016.
- Skype empresarial actualizado local 2015, con CU9 6.0.9319.548 (mayo de 2019) o posterior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización de superseding), o 2012 R2.
- Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o posterior, instrucciones [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Aplicación de sucursal con funciones de supervivencia (SBA) con Skype Empresarial Server 2015 CU6 HF2 o posterior (confirme con su proveedor que empaquetaron las actualizaciones adecuadas y que se han puesto a disposición de su dispositivo)
- Servidor de sucursal con funciones de supervivencia (SBS) con Skype Empresarial Server 2015 CU6 HF2 o posterior
- Solo rol perimetral de Lync Server 2013 , esto se debe a que el rol perimetral no tiene una dependencia de Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente probados y compatibles

- Cliente de escritorio de Lync 2013 (Skype Empresarial), MSI y C2R, incluidos basic [15.0.5023.1000 o posterior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Cliente de escritorio de Skype Empresarial 2016, MSI [16.0.4678.1000 o](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)posterior, incluido Basic
- Skype Empresarial 2016 Haga clic para ejecutar Requerir las actualizaciones de abril [de 2018:](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 
    - Mensual y Semi-Annual dirigida, 16 \. 0 \. 9126 \. 2152 o superior
    - Semi-Annual y canal diferido, 16 \. 0 \. 8431 \. 2242 o posterior
- Skype Empresarial en Mac 16.15 o posterior
- Skype Empresarial para iOS y Android 6.19 o posterior
- Salas de Microsoft Teams (anteriormente conocidas como Sistema de salas de Skype V2 SRS V2) 4.0.64.0 (diciembre de 2018) o posterior
- Actualización de Surface Hub para team edition basada en KB4499162 (mayo de 2019, compilación del sistema operativo 15063.1835) o posterior
- Skype Web App 2015 CU6 HF2 o superior (se incluye con servidor)

### <a name="currently-being-investigated"></a>Actualmente se está investigando

- Panel de calidad de llamadas (nueva instalación después de deshabilitar TLS 1.0, 1.1, vea a continuación)*
 
### <a name="out-of-scope"></a>Fuera de ámbito

Excepto donde se indica, los siguientes productos no están en el ámbito de la deshabilitación de TLS 1.0/1.1 y no funcionarán en un entorno donde SEL 1.0 y 1.1 se hayan deshabilitado. Esto significa: si sigue utilizando clientes o servidores fuera del ámbito, debe actualizarlos o quitarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de la implementación local de Skype Empresarial Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 o inferior
- Lync para Mac 2011
- Lync 2013 para dispositivos móviles: iOS, iPad, Android o Windows Phone
- Cliente de la Tienda Windows Lync "MX"
- Sistema de sala de Lync (a.k.a. SRSv1). LRS llegó al final de la compatibilidad el 9 de octubre de 2018 y no se actualizará para admitir TLS 1.2.
- Todos los clientes de Lync 2010
- Lync Phone Edition: guía actualizada [aquí.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- Aplicación de sucursal con funciones de supervivencia (SBA) basada en 2013 o servidor de sucursal con funciones de supervivencia (SBS)
- Cloud Connector Edition (CCE)
- Skype Empresarial para Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 depende de Windows Fabric versión 1.0.  En la fase de diseño de Lync Server 2013, Se eligió Windows Fabric 1.0 por su atractiva y nueva arquitectura distribuida para proporcionar replicación, alta disponibilidad y tolerancia a errores.  Con el tiempo, Tanto Skype Empresarial Server como Windows Fabric han mejorado enormemente esta arquitectura conjunta con un diseño significativo en versiones posteriores.  El Skype Empresarial 2015 Server actual usa Windows Fabric 3.0, por ejemplo.

Desafortunadamente, Windows Fabric 1.0 **no es compatible con TLS 1.2.  Sin embargo, actualizaremos Lync Server 2013 para que funcione con TLS 1.2**. Esto aparecerá en la próxima actualización acumulativa para Lync Server 2013.  Proporcionamos compatibilidad con TLS 1.2 para habilitar escenarios híbridos, de migración, de migración y de coexistencia.

Si su organización tiene que deshabilitar TLS 1.0 y 1.1 y actualmente usa Lync Server 2013, le recomendamos que inicie el proceso de planeación, con la posibilidad de que tenga que actualizar localmente o migrar en paralelo (nuevos grupos de servidores, mover usuarios) a Skype Empresarial Server 2015 o posterior.  O quizás quiera acelerar la migración a Skype Empresarial Online.

#### <a name="call-quality-dashboard"></a>Panel de calidad de llamadas

El Panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1.0 durante la nueva instalación (primera vez que se instala en los entornos locales).  Actualmente estamos investigando este problema y planeamos publicar una corrección en un futuro próximo.  Si planea instalar CQD y deshabilitar TLS 1.0, le recomendamos que complete primero la instalación de CQD y, a continuación, continúe con la deshabilitación de TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Administrador de SDN de Skype Empresarial

El Administrador de SDN de Skype Empresarial SQL una base de datos depende de TLS 1.0 durante la nueva instalación. Si planea instalar el Administrador de SDN de Skype Empresarial con SQL una base de datos y también deshabilitar TLS 1.0, se recomienda completar primero el Administrador de SDN de Skype Empresarial y, a continuación, continuar con la deshabilitación de TLS 1.0. En caso de que TLS 1.0 se deshabilite antes de la instalación, debe habilitar temporalmente TLS 1. SQL Server 0 de nuevo en un servidor back-end que se usará para hospedar la base de datos del Administrador de SDN de Skype Empresarial SQL.

#### <a name="third-party-devices"></a>Dispositivos de terceros

En dispositivos de terceros, como teléfonos 3PIP, videoconferencias, servidores proxy inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1.2, probar detenidamente y ponerse en contacto con el proveedor si es necesario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Consideraciones de federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales

Debe planear cuidadosamente y considerar el impacto de deshabilitar TLS 1.0/1.1 en los servidores perimetrales.  Una vez que TLS 1.0 y 1.1 están deshabilitados, es posible que encuentre que otras organizaciones ya no pueden federar con su organización.

Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con versiones anteriores con sistemas externos no parcheados (SfB 2015, Lync 2013) o anteriores (2010).

Microsoft no puede proporcionar consejos ni recomendaciones sobre si la red perimetral (o cualquier red) está bajo el estándar PCI; que debe ser determinada por la empresa individual.

Skype Empresarial Online es capaz de TLS 1.2 hoy en día, por lo que no se espera ningún impacto en la federación híbrida con Online.

PIC (conectividad de mensajería instantánea pública) con el servicio de consumidor de Skype: no esperamos que deshabilitar TLS 1.0/1.1 repercuta en la conectividad [de Skype;](../../deploy/deploy-skype-connectivity.md) Las puertas de enlace de Microsoft PIC ya son compatibles con TLS 1.2.

## <a name="prerequisites-and-process"></a>Requisitos previos y proceso

Excepto donde se indica anteriormente, una vez que TLS 1.0 y 1.1 están deshabilitados servidores fuera del ámbito, los clientes y dispositivos funcionarán más tiempo correctamente o en absoluto. Esto puede significar que debes pausar y esperar a que Microsoft te actualice las instrucciones. Una vez que esté satisfecho de que cumple todos los requisitos y tiene un plan para solucionar las diferencias, continúe.

En un nivel alto, mientras Skype Empresarial Server 2019 está listo para el procedimiento en la instalación, Skype Empresarial Server 2015 requerirá instalar CU9, aplicar actualizaciones previas a .NET y SQL, implementar claves de registro de requisitos previos y, por último, una ronda independiente de actualizaciones de configuración del sistema operativo (es decir, deshabilitar TLS 1.0 y 1.1 mediante la importación de archivos del Registro). Es fundamental que complete la instalación de todos los requisitos previos, incluido Skype Empresarial Server 2015 CU6 HF2, antes de deshabilitar TLS 1.0 y 1.1 en cualquier servidor de su entorno. Todos los servidores de Skype Empresarial, incluidos los roles perimetrales y SQL back-end, requieren las actualizaciones. Asegúrese también de que todos los clientes compatibles (en el ámbito) se hayan actualizado a las versiones mínimas necesarias. No olvide actualizar las estaciones de trabajo de administración también.

Queremos seguir el orden habitual de las operaciones de "inside out" para actualizar los servidores de Skype Empresarial. Trate grupos de directores, chat persistente y grupos emparejados de la misma manera que lo haría normalmente. El orden y los métodos de actualización se tratan [aquí](topology.md) [y aquí](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Proceso de alto nivel

1. Pruebe todos los pasos del laboratorio antes de configurar los servidores de producción.
2. Haga una copia de seguridad y conserve una copia del Registro exportado en todos y cada uno de los servidores que se actualizarán. No puede compartir registros entre servidores; contienen claves únicas basadas en máquinas.
3. Actualice todos los servidores de Skype Empresarial 2015 a CU9 o posterior. Para Skype Empresarial Server 2019, actualice a CU1 o posterior.
4. Instale todos los requisitos previos en todos los servidores.
5. Implementar claves del Registro de requisitos previos.
6. Asegúrese de que todos los clientes del ámbito estén actualizados.
7. Deshabilite TLS 1.0 y 1.1 mediante la importación del Registro.
8. Valide que las cargas de trabajo funcionan según lo esperado.
    - Si se encuentran problemas, solucionar y solucionar problemas, o
    - Restaurar el Registro desde el paso 2 para volver a habilitar TLS 1.0 y 1.1
9. Valide que solo se esté utilizando TLS 1.2.

### <a name="install-prerequisites-to-all-servers"></a>Instalar requisitos previos en todos los servidores

Es necesaria una actualización extensiva de dependencias antes de empezar a deshabilitar TLS 1.0 y 1.1 en el nivel del sistema operativo en las implementaciones de Skype Empresarial Server 2015. Las siguientes son las versiones mínimas que pueden admitir TLS 1.2. Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype Empresarial del entorno antes de empezar a deshabilitar TLS 1.0 y 1.1.

- Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o posterior
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) o posterior con SchUseStrongCrypto habilitado en el Registro (proporcionado a continuación)
- SQL debe actualizarse en todos los servidores y back-end de Skype Empresarial 2015. Actualice el grupo de servidores de Enterprise Edition SQL back-end primero y, a continuación, sus respectivas FEs. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), o superior / SQL Server 2012 SP2 + CU16 o superior / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), o superior / SQL Server 2014 SP2
     - [SQL Server native client for SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Controlador ODBC de Microsoft 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), o posterior
     - [Objetos de administración compartidos para SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes para SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Pasos básicos para instalar requisitos previos, en el orden recomendado de las operaciones

1. Instale la actualización cu9 de Skype Empresarial Server en todos los servidores. 
    1. Instale la actualización en los componentes mediante el actualizador.
    2. Actualice las bases de datos de acuerdo con los procedimientos documentados. Para Skype Empresarial Server 2015, vea KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valide la funcionalidad del producto en la implementación antes de avanzar con cualquier otro cambio.
2. Descargue .NET 4.7 Offline Installer. 
    1. Referencia: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Asegúrese de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end.
    3. Referencia: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Ejecute el paquete del instalador.
    7. Reinicie el servidor.
3. Actualice SQL Express 2014 en todos los servidores. 
    1. Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Descargar SQL 2014 SP2 
        - Referencia: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copie el medio de instalación en una carpeta del servidor (por ejemplo, C:\01_2014SqlSp2)
    4. Asegúrese de que los servicios de Skype Empresarial Server 2015 se detengan en el servidor front-end 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Abra un símbolo del sistema de administración y actualice todos los componentes e instancias instalados 
        - Ejemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Actualice SQL native client. 
    1. Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Descargar desde [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Asegúrese de que los servicios de Skype Empresarial Server 2015 se detengan en el servidor front-end. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Detener la ejecución SQL instancias instaladas 
        - Por ejemplo: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Por ejemplo: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Instale el paquete.
5. Actualice el controlador ODBC 11 para SQL Server para incluir compatibilidad con TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Descargar [odbc driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Asegúrese de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end.
        - Ejemplo (Standard Edition): ```Stop-CsWindowsService```
        - Ejemplo (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Instale el paquete.
6. Implementar claves del Registro de requisitos previos.

### <a name="pre-requisite-registry-keys"></a>Claves del Registro de requisitos previos

Copie o pegue la siguiente prueba en el Bloc de notas y cambie el nombre tlsPreReq.reg o un nombre de su elección y luego importe:

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

Para SQL back-end para grupos de servidores Enterprise Edition, los requisitos previos y la deshabilitación de TLS deben tratarse como cualquier SQL actualizaciones del sistema operativo; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Aunque se pueden combinar los pasos de deshabilitación de TLS y la aplicación de requisitos previos, recomendamos encarecidamente que se apliquen todos los requisitos previos antes de continuar con la deshabilitación de TLS 1.0 y 1.1 en el nivel del sistema operativo. El método recomendado sería preparar el entorno implementando todos los requisitos previos, validando que todas las cargas de trabajo funcionen correctamente y según lo esperado y, a continuación, continuar con la deshabilitación de TLS 1.0/1.1 más adelante.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deshabilitar TLS 1.0 y 1.1 mediante la importación del Registro

Antes de continuar con los pasos siguientes, asegúrese de que ha completado todos los *requisitos previos y* actualizado Skype Empresarial Servers .

Copie el siguiente texto en un archivo del Bloc de notas y cambie el nombre **tlsDisable.reg**:

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

Importe el archivo .reg en cada servidor que desee deshabilitar TLS 1.0 y 1.1. Reinicie el servidor. Una vez que los servicios vuelvan a estar en línea, muévete al siguiente servidor. El enfoque de los grupos de servidores de Enterprise Edition es el mismo que se tomaría para cualquier actualización del sistema operativo.

Puede que haya notado que estamos haciendo algo más que deshabilitar TLS 1.0 y 1.1 aquí. Estamos soportando el reojo de conjunto de cifrado (como se muestra anteriormente) y la deshabilitación de algunos cifrados débiles más antiguos. Es la primera vez que se admiten oficialmente estos cambios en SCHANNEL y API de criptografía en Skype Empresarial Server, y es importante tener en cuenta que estos cambios son los únicos que admitemos y hemos probado en este momento. Podemos considerar configuraciones adicionales en el futuro, pero por ahora, no modifique el archivo de importación del Registro en su implementación.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que las cargas de trabajo funcionan según lo esperado

Una vez que TLS 1.0 y 1.1 se hayan deshabilitado en su entorno, asegúrese de que todas las cargas de trabajo principales funcionan según lo esperado, como im & Presence, llamadas P2P, Telefonía IP empresarial, etc.

**Validar que solo se usa TLS 1.2**

Haga que el equipo de seguridad realice una nueva auditoría del tráfico de Skype Empresarial para asegurarse de que los protocolos anteriores TLS 1.0 y 1.1 ya no están en uso.

Como alternativa, puede usar Internet Explorer para probar conexiones TLS a servicios web desde Skype Empresarial Server 2015 después de deshabilitar TLS 1.0 y TLS 1.1.

1. Inicie Internet Explorer.
2. Seleccione **Herramientas Opciones** de  >  **Internet**.
3. Seleccione la **pestaña** Avanzadas.
4. En **Configuración**, desplácese hasta la parte inferior.
5. Compruebe que TLS 1.0, TLS 1.1 y TLS 1.2 están habilitados.
6. Examine la dirección URL del servicio web interno del grupo de servidores de SfB 2015 (debe conectarse correctamente).
7. Vuelva a Internet Explorer y deshabilite la opción **usar solo TLS 1.2.**
8. Examine de nuevo la dirección URL del servicio web interno del grupo de servidores de SfB 2015 (no debería conectarse).

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Escenarios de implementación avanzada

Dado que algunos requisitos previos de dependencia son necesarios para admitir TLS 1.2 en Skype Empresarial Server 2015, la instalación desde medios RTM producirá un error en cualquier sistema en el que se hayan deshabilitado TLS 1.0 y 1.1.

**Implementación de nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que TLS 1.0 y 1.1 se han deshabilitado en su entorno.**

**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los archivos binarios de SQL actualizados en una CU futura y actualizaremos este artículo en el futuro.

**Opción 2:** Preinstalar instancias SQL locales (RTCLOCAL y LYNCLOCAL)

1. Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64.exe) en la carpeta local de FE. Supongamos que la ruta de acceso de carpeta <SQL_FOLDER_PATH>.
2. Inicie PowerShell o símbolo del sistema y vaya a <SQL_FOLDER_PATH>.
3. Cree la instancia de SQL RTCLOCAL ejecutando el siguiente comando. Espere hasta SQLEXPR_x64.exe finaliza antes de continuar:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Cree la instancia de SQL LYNCLOCAL ejecutando el siguiente comando. Espere hasta SQLEXPR_x64.exe finaliza antes de continuar con el paso siguiente:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Ejecute el programa de instalación de Skype Empresarial Server 2015 RTM.
2. Siga los pasos restantes de la sección de requisitos previos anterior.

**Opción 3:** También puede reemplazar manualmente los archivos binarios en un directorio multimedia de instalación local de la siguiente manera:

1. [Instalar requisitos previos para Skype Empresarial Server](../../deploy/install/install-prerequisites.md)  
2. Instalar .NET 4.7: 
      - **Nota:** Introdujimos por primera vez compatibilidad con .NET 4.7 en Skype Empresarial Server 2015 CU5 (6.0.9319.281). Por lo tanto, en los pasos posteriores que se indican a continuación, actualizaremos componentes principales antes de la instalación principal.
      - Descargar: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referencia: Software que debe instalarse antes de una implementación de [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiar archivos o carpetas ISO: 
    - Con la ISO de Skype Empresarial Server 2015 adjunta, abra el directorio raíz de la unidad que está adjunta como (Por ejemplo: D: \) en el Explorador de archivos.
    - Copie todas las carpetas y archivos en una carpeta de un disco local (por ejemplo: C:\SkypeForBusiness2015ISO).
    - **Nota:** Antes de instalar componentes, algunos archivos tendrán que actualizarse para admitir TLS 1.2.
4. Reemplazar paquetes MSI/EXE: 
    - Reemplace los paquetes MSI y EXE existentes en la carpeta /Setup/amd64/ del medio de instalación en el equipo local.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Cambie el SQLEXPR_x64 a la máquina local y reemplace el archivo existente en la carpeta Setup/amd64/ del medio de instalación.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Nota:** Cambie el nombre si es necesario sqlncli.msi y, a continuación, reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.
    - SQL objetos de administración: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccione para descargar SharedManagementObjects.msi solo.
        - **Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.
    - SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar. Seleccione para descargar CQLSysClrTypes.msi solo
        - **Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.
5. Instalar componentes principales: 
    - Ejecute Setup.exe desde la carpeta Setup/amd64/ del medio de instalación. Siga las instrucciones para instalar componentes principales
    - Cerrar componentes principales.
6. Actualizar componentes principales: 
    - Descargue el Instalador de actualización de Skype Empresarial.
    - Ejecute el instalador para actualizar componentes principales e instalar los contadores de rendimiento.
    - **Nota:** Desde la versión de CU6HF2, la característica de actualización automática actualmente solo se instalará hasta CU6. Por lo tanto, el actualizador debe ejecutarse por separado para actualizar componentes principales a 6.0.9319.516.
    - Referencia: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar herramientas administrativas (opcional): 
    - Esto instalará los tipos Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) y Microsoft System CLR Types for SQL Server 2014 (x64) mediante los archivos actualizados. Además, el Generador de topologías y el Panel de control de Skype Empresarial Server 2015 estarán disponibles en el equipo local.
8. Instalar el almacén de configuración local (paso 1): 
     - Abra el Asistente para implementación, haga clic en Instalar o actualizar el sistema de Skype Empresarial Server y haga clic en **Ejecutar** en paso 1: Instalar almacén de configuración local.
     - Haga **clic en Siguiente** en el cuadro de diálogo Instalar almacén **de** configuración local.
     ![Cuadro de diálogo Instalar almacén de configuración local](../../media/local-configuration-store.png)
     - Revise los resultados y asegúrese de que el estado de la tarea está completado. Revise el archivo de registro resultante haciendo clic **en Ver registro**.
     ![El estado de la tarea se muestra como Completado](../../media/local-configuration-task-completed.png)
     - Haga clic en **Finalizar**.
9. Configurar o quitar componentes de Skype Empresarial Server (paso 2):
    - Abra el Asistente para implementación, haga clic en  Instalar o actualizar Skype Empresarial **Server System** y haga clic en Ejecutar en paso 2: Configurar o quitar componentes de Skype Empresarial Server
    - Haga **clic en** Siguiente en el cuadro de diálogo Configurar componentes de Skype Empresarial Server.
    ![la ventana Configurar componentes de Skype Empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Revise el registro con View Log y valide que la instalación se completó sin problemas. 
    - Haga clic en **Finalizar**.
10. Continúe con la instalación y configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).
