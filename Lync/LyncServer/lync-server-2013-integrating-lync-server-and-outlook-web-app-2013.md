---
title: 'Lync Server 2013: integración de Lync Server y Outlook Web App 2013'
description: 'Lync Server 2013: integración de Lync Server y Outlook Web App 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d9c7e91dba22f78325eaddc5b5d7469ccf4cc92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567396"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-03_

Además de integrarse con Microsoft Outlook 2013, Microsoft Lync Server 2013 puede integrarse completamente con Microsoft Outlook Web App 2013; entre otras cosas, esto agrega mensajería instantánea y presencia a Outlook Web App y permite que la lista de contactos unificada se comparta entre Outlook Web App y Microsoft Lync 2013. Para integrar Lync Server 2013 y Outlook Web App, primero debe comprobar que se ha instalado el tiempo de ejecución de la API administrada de comunicaciones unificadas 4,0 en el servidor back-end de Microsoft Exchange Server 2013. Puede hacerlo buscando si existe el siguiente valor del registro:

HKEY \_ local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ InstantMessaging \\ ImplementationDLLPath

ImplementationDLLPath debe apuntar a la ubicación de la carpeta para el archivo Microsoft.Rtc.Internal.Ucweb.dll. Si no es así, o si el valor del registro no existe, debe descargar e instalar el programa de instalación de la ejecución de UCMA desde el centro de descarga de Microsoft en <https://www.microsoft.com/download/details.aspx?id=34992> . Encontrará información sobre cómo instalar el tiempo de ejecución de UCMA en la misma página web.

**Compatibilidad con versiones anteriores**

Lync Server 2013 puede integrarse con las versiones de Microsoft Exchange Server 2010 de mensajería unificada y Outlook Web App. Para obtener más información, vea el artículo Deploying on-premises Exchange UM to proporcionar Lync Server 2010 voice mail en [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) . Si se integra con Exchange 2010, no tendrá características específicas de Lync Server, como el almacén de contactos unificado y el archivado de Lync a Exchange.

Microsoft Lync 2013 también se puede usar junto con Exchange 2010 y Outlook 2010. De nuevo, sin embargo, las nuevas funciones, como el almacén de contactos unificado y las fotos de alta resolución, no estarán disponibles para los usuarios de Lync 2013. Estas nuevas funciones requieren tanto Lync Server 2013 como Exchange 2013.

**Creación de un grupo de aplicaciones de confianza para Outlook Web App**

Si ha instalado el servicio de enrutador de llamadas de mensajería unificada de Microsoft Exchange y el servicio de mensajería unificada de Microsoft Exchange en el mismo equipo, no es necesario crear un grupo de aplicaciones de confianza para Outlook Web App. (Esto supone que el servidor en cuestión hospeda un plan de marcado de mensajería unificada de SipName). Si usa un solo equipo para hospedar ambos servicios, puede ir a la sección de este documento titulada habilitación de la **mensajería instantánea en Outlook Web App**.

Lync Server 2013 puede detectar automáticamente cualquier servidor de Exchange que hospede un plan de marcado de mensajería unificada de SipName; Estos servidores se agregan automáticamente a la lista de servidores conocidos de Lync Server. No es necesario crear un grupo de aplicaciones de confianza y agregar estos servidores a la lista de servidores conocidos. De hecho, esto hará que la integración de Outlook Web App deje de funcionar.

<div>


> [!NOTE]  
> Esto se debe al hecho de que la topología de Lync Server ahora tendrá dos entradas para el mismo equipo: la entrada de detección automática y la entrada agregada manualmente. Para solucionar el problema y volver a funcionar Outlook Web App, use Windows PowerShell para quitar las entradas del grupo de confianza y de la aplicación de confianza para el servidor. Consulte los temas de ayuda de los cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obtener más información.



</div>

Si estos dos servicios se ejecutan en equipos independientes, después de haber comprobado que se ha instalado el tiempo de ejecución de la API administrada de comunicaciones unificadas 4,0, debe crear un grupo de aplicaciones de confianza de Lync Server y una aplicación de confianza asociada con Outlook Web App; de este se agregará el servidor a la lista de servidores conocidos. Para ello, primero ejecute un comando similar a este desde dentro del shell de administración de Lync Server:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

En el comando anterior, atl-owa-001.litwareinc.com es el nombre de dominio completo del grupo de Outlook Web App; debe ser el mismo nombre que aparece en los campos nombre de sujeto y nombre alternativo de sujeto (SAN) del certificado que proporciona acceso a Outlook Web App. Del mismo modo, atl-cs-001.litwareinc.com es el nombre de dominio completo del grupo de servidores de Lync 2013 que hospedará el nuevo grupo de aplicaciones de confianza. Tenga en cuenta que el sitio especificado, Redmond, representa el SiteID del sitio de Lync Server. El SiteID no es necesariamente el mismo que el DisplayName del sitio; puede recuperar SiteIDs para los sitios de Lync Server ejecutando el siguiente comando desde el shell de administración de Lync Server:

    Get-CsSite | Select-Object DisplayName, SiteID

Después de crear el grupo de aplicaciones de confianza, use un comando similar al siguiente para configurar una identidad de aplicación y un puerto para Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

En el comando anterior, ApplicationID simplemente es un identificador fácil de usar usado para distinguir las aplicaciones de confianza. ApplicationID puede ser cualquier cadena de texto que no incluya espacios en blanco u otros caracteres prohibidos. (Para garantizar la creación de un identificador válido, se recomienda que use solo letras y números al especificar un ApplicationID). El valor asignado al parámetro Port también queda a discreción del administrador: puede ser cualquier puerto disponible de la red.

Después de crear la aplicación de confianza, debe ejecutar el siguiente comando para habilitar los cambios en la topología de Lync Server:

    Enable-CsTopology

Tenga en cuenta que también debe agregar su servidor de buzones y de acceso de cliente de Exchange a todos los planes de marcado de URI de SIP. A su vez, se configurarán los servidores como interlocutores SIP de confianza con la topología ExUmRouting para Lync Server.

**Habilitación de la mensajería instantánea en Outlook Web App**

Con Lync Server correctamente configurado puede empezar a configurar Outlook Web App. El primer paso de ese proceso es habilitar la mensajería instantánea en todos los directorios virtuales de Outlook Web App en los servidores front-end. (No es necesario habilitar la mensajería instantánea para los directorios virtuales de los servidores back-end. De hecho, se recomienda no habilitar la mensajería instantánea en los servidores back-end. La mensajería instantánea se puede habilitar en los servidores de acceso de cliente mediante la ejecución del siguiente comando desde el shell de administración de Exchange:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> De forma predeterminada, la mensajería instantánea está habilitada al instalar Outlook Web App; es decir, la propiedad InstantMessagingEnabled se establece en true. Sin embargo, aún debe ejecutar el comando anterior para establecer el tipo de mensajería instantánea en OCS. De forma predeterminada, InstantMessagingType se establece en none.



</div>

A continuación, debe agregar las dos líneas siguientes al archivo de Web.config de Outlook Web App (este archivo suele estar en la carpeta C: \\ archivos de programa \\ Microsoft \\ Exchange Server \\ inquilino V15 \\ ClientAccess \\ OWA). Estas dos líneas deben agregarse en el \<AppSettings\> nodo del archivo Web.config, y este procedimiento solo debe realizarse en los servidores back-end donde se haya instalado Outlook Web App:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

En el ejemplo anterior, el valor de IMCertificateThumbprint debe ser la huella digital del certificado de Exchange 2013 que está instalado en los servidores back-end. Puede recuperar dicha información si ejecuta el siguiente comando desde el shell de administración de Exchange:

    Get-ExchangeCertificate

Tenga en cuenta que el valor asignado a inservername es el nombre de dominio completo del grupo de servidores de Lync Server en el que se creó el grupo de aplicaciones de confianza para Outlook Web App.

El certificado que use para Outlook Web App debe ser un certificado que sea de confianza para Lync Server. Una forma de garantizar que el certificado sea de confianza tanto para Lync Server como para Exchange es usar la entidad de certificación interna para crear un certificado en el servidor de buzones de correo, asegurándose de que el FQDN del servidor se use para el nombre del sujeto y que este FQDN aparezca en el campo Nombre alternativo del certificado. Una vez creado el certificado, se puede importar a los servidores back-end. El resultado de la red es que el mismo certificado se usa para dos propósitos: 1) comunicación entre la mensajería unificada de Exchange y Lync Server; y 2) la integración entre Outlook Web App y Lync Server.

Después de actualizar el archivo de Web.config, debe ejecutar el siguiente comando en el servidor back-end de Exchange para reciclar el grupo de Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Si la operación de reciclaje se realiza correctamente, verá el siguiente mensaje en el shell de administración de Exchange:

    "MSExchangeOWAAppPool" successfully recycled

**Configuración de directivas de buzón de Outlook Web App**

En este momento, puede usar el siguiente comando para configurar la mensajería instantánea en la Directiva de buzones de correo de Outlook Web App correspondiente (o directivas). Por ejemplo, este comando, que se ejecuta en uno de los servidores de buzones de correo, habilita la mensajería instantánea en la directiva predeterminada:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Y este comando permite la mensajería instantánea para todas las directivas de buzón de Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Una vez habilitada la Directiva de buzón, todos los usuarios administrados por esa Directiva tendrán una integración completa entre Lync Server y Outlook Web App, siempre que:

  - El usuario tiene un buzón en Exchange 2013.

  - El usuario se ha habilitado para Lync Server 2013.

  - El usuario tiene una dirección de proxy SIP válida.

**Deshabilitar la mensajería instantánea en Outlook Web App**

Como se indicó anteriormente, la mensajería instantánea está habilitada de forma predeterminada en Outlook Web App. Esto significa que, si no integra Outlook Web App con Lync Server, los usuarios verán iconos de presencia en blanco y un mensaje de error cada vez que inicien sesión en Outlook Web App. Para evitar este problema, use el siguiente comando de Shell de administración de Exchange para deshabilitar la mensajería instantánea en Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Comprobación de la integración con Outlook Web App**

Para comprobar que la mensajería instantánea y la presencia se han integrado con Outlook Web App, inicie sesión en Outlook Web App 2013. En la esquina superior derecha de la pantalla, verá su nombre para mostrar de Exchange. Si aparece un icono de presencia junto a su nombre (por ejemplo, un icono verde que indica que su estado actual es disponible) que indica que ha integrado correctamente Lync Server y Outlook Web App.

Después del inicio de sesión inicial en Outlook Web App, compruebe si se ha escrito un evento con el identificador de evento 112 (y el origen de MSExchange OWA) en el registro de eventos del servidor de buzones de correo. Este evento indica que el administrador de extremos de mensajería instantánea se inicializó correctamente. Si la mensajería instantánea no parece funcionar, en el servidor de buzones de correo, busque archivos de registro en la carpeta C: \\ archivos de programa \\ Microsoft \\ Exchange Server \\ inquilino V15 registro de \\ \\ OWA \\ InstantMessaging. Si no existen las carpetas Logging o InstantMessaging que indican que se ha producido un error en la integración. En ese caso, puede usar el seguimiento de SIPStack en Lync Server (todos los niveles y todos los indicadores) para probar y determinar por qué se produjo un error en la integración.

</div>

<span> </span>

</div>

</div>

</div>

