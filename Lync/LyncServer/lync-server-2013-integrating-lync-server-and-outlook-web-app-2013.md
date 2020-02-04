---
title: 'Lync Server 2013: integración de Lync Server y Outlook Web App 2013'
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
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-03_

Además de integrarse con Microsoft Outlook 2013, Microsoft Lync Server 2013 puede integrarse completamente con Microsoft Outlook Web App 2013; entre otras cosas, esto agrega mensajería instantánea y presencia a Outlook Web App y permite que la lista de contactos unificada se comparta entre Outlook Web App y Microsoft Lync 2013. Para integrar Lync Server 2013 y Outlook Web App, primero debe comprobar que el tiempo de ejecución de la API administrada de comunicaciones unificadas 4,0 se ha instalado en el servidor back-end de Microsoft Exchange Server 2013. Para ello, busque la existencia del siguiente valor del registro:

HKEY\_local\_Machine\\System\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath debe apuntar a la ubicación de la carpeta del archivo Microsoft.Rtc.Internal.Ucweb.dll. Si no lo hace, o si el valor del registro no existe, debe descargar e instalar el programa de instalación de tiempo de ejecución de UCMA desde el centro <http://www.microsoft.com/en-us/download/details.aspx?id=34992>de descarga de Microsoft en. En la misma página web, encontrará información sobre cómo instalar UCMA Runtime.

**Compatibilidad con versiones anteriores**

Lync Server 2013 se puede integrar con las versiones de Microsoft Exchange Server 2010 de mensajería unificada y Outlook Web App. Para obtener más información, vea el artículo implementar la mensajería unificada de Exchange local para proporcionar el correo de voz [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)de Lync Server 2010. Si se integra con Exchange 2010, no tendrá características específicas de Lync Server, como el almacenamiento de contactos unificado y el archivado de Lync a Exchange.

Microsoft Lync 2013 también se puede usar conjuntamente con Exchange 2010 y Outlook 2010. De nuevo, sin embargo, las nuevas funciones, como el almacenamiento de contactos unificado y las fotos de alta resolución, no estarán disponibles para los usuarios de Lync 2013. Estas nuevas capacidades requieren Lync Server 2013 y Exchange 2013.

**Creación de un grupo de aplicaciones de confianza para Outlook Web App**

Si ha instalado el servicio de enrutamiento de llamadas de mensajería unificada de Microsoft Exchange y el servicio de mensajería unificada de Microsoft Exchange en el mismo equipo, no es necesario crear un grupo de aplicaciones de confianza para Outlook Web App. (Esto supone que el servidor en cuestión hospeda un plan de marcado de mensajería unificada de SipName). Si está usando un solo equipo para hospedar ambos servicios, puede ir a la sección de este documento titulada **habilitación de la mensajería instantánea en Outlook Web App**.

Lync Server 2013 puede descubrir autodescubrimiento de cualquier servidor de Exchange que hospede un plan de marcado de MU de SipName; Estos servidores se agregan automáticamente a la lista de servidores conocidos de Lync Server. No es necesario crear un grupo de aplicaciones de confianza y agregar estos servidores a la lista de servidores conocidos. De hecho, esto hará que la integración de Outlook Web App deje de funcionar.

<div>


> [!NOTE]  
> Esto se debe al hecho de que la topología de Lync Server ahora tendrá dos entradas para el mismo equipo: la entrada autodiscovered y la entrada agregada manualmente. Para corregir el problema y lograr que Outlook Web App vuelva a funcionar, use Windows PowerShell para quitar las entradas del grupo de confianza y de la aplicación de confianza para el servidor. Consulte los temas de Ayuda acerca de los cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obtener más información.



</div>

Si estos dos servicios se ejecutan en equipos diferentes, después de comprobar que se ha instalado la API administrada de comunicaciones unificadas 4,0 Runtime, debe crear un grupo de aplicaciones de confianza de Lync Server y una aplicación de confianza asociada con Outlook Web App; que agregará el servidor a la lista de servidores conocidos. Para ello, primero ejecute un comando similar a este desde el shell de administración de Lync Server:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

En el comando anterior, atl-owa-001.litwareinc.com es el nombre de dominio completo del grupo de Outlook Web App; debe ser el mismo nombre que aparece en los campos nombre del asunto y nombre alternativo del sujeto (SAN) del certificado que proporciona acceso a Outlook Web App. Del mismo modo, atl-cs-001.litwareinc.com es el nombre de dominio completo del grupo de servidores de Lync Server 2013 que hospedará el nuevo grupo de aplicaciones de confianza. Tenga en cuenta que el sitio especificado, Redmond, representa el SiteID del sitio de Lync Server. El SiteID no es necesariamente el mismo que el DisplayName del sitio; puede recuperar SiteIDs para los sitios de Lync Server ejecutando el siguiente comando desde el shell de administración de Lync Server:

    Get-CsSite | Select-Object DisplayName, SiteID

Después de crear el grupo de aplicaciones de confianza, use un comando similar al siguiente para configurar una identidad de aplicación y un puerto para Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

En el comando anterior, ApplicationID simplemente es un identificador fácil de usar usado para distinguir las aplicaciones de confianza. ApplicationID puede ser cualquier cadena de texto que no incluya espacios en blanco u otros caracteres prohibidos. (Para garantizar la creación de un identificador válido, se recomienda que use solo letras y números al especificar un ApplicationID). El valor asignado al parámetro Port también queda a discreción del administrador: puede ser cualquier puerto disponible de la red.

Después de crear la aplicación de confianza, debe ejecutar el siguiente comando para habilitar los cambios en la topología de Lync Server:

    Enable-CsTopology

Tenga en cuenta que también debe agregar su servidor de buzón y acceso de cliente de Exchange a todos los planes de marcado de URI del SIP. A su vez, se configurarán los servidores como interlocutores SIP de confianza con la topología ExUmRouting para Lync Server.

**Habilitar la mensajería instantánea en Outlook Web App**

Si Lync Server se ha configurado correctamente, puede empezar a configurar Outlook Web App. El primer paso de ese proceso es habilitar la mensajería instantánea en todos los directorios virtuales de Outlook Web App de sus servidores front-end. (No es necesario habilitar la mensajería instantánea para los directorios virtuales de los servidores back-end. De hecho, se recomienda no habilitar la mensajería instantánea en los servidores de back-end.) La mensajería instantánea se puede habilitar en los servidores de acceso de cliente ejecutando el siguiente comando desde el shell de administración de Exchange:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> De manera predeterminada, la mensajería instantánea se habilita al instalar Outlook Web App; es decir, la propiedad InstantMessagingEnabled se establece en True. Sin embargo, aún debe ejecutar el comando anterior para establecer el tipo de mensajería instantánea en OCS. De manera predeterminada, InstantMessagingType está establecido en None.



</div>

A continuación, debe agregar las dos líneas siguientes al archivo Web. config de Outlook Web App (este archivo suele encontrarse en la\\carpeta C\\:\\archivos de\\programa\\Microsoft\\Exchange Server V15 ClientAccess OWA). Estas dos líneas deben agregarse en el \<nodo\> appSettings del archivo Web. config, y este procedimiento solo debe realizarse en los servidores back-end donde se haya instalado Outlook Web App:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

En el ejemplo anterior, el valor de IMCertificateThumbprint debe ser la huella digital para el certificado de Exchange 2013 que está instalado en los servidores de back-end. Para recuperar esa información, ejecute el siguiente comando desde el shell de administración de Exchange:

    Get-ExchangeCertificate

Tenga en cuenta que el valor asignado a inservername es el nombre de dominio completo del grupo de servidores de Lync en el que creó el grupo de aplicaciones de confianza para Outlook Web App.

El certificado que use para Outlook Web App debe ser un certificado de confianza de Lync Server. Una forma de garantizar que el certificado será de confianza tanto en Lync Server como en Exchange es usar la entidad emisora de certificados interna para crear un certificado en el servidor de buzones, asegurándose de que el FQDN del servidor se use para el nombre del sujeto y de que este FQDN aparezca en t el campo Nombre alternativo de certificado. Una vez creado el certificado, puede importarse a los servidores back-end. El resultado neto es que el mismo certificado se usa para dos propósitos: 1) comunicación entre la mensajería unificada de Exchange y Lync Server; y 2) la integración entre Outlook Web App y Lync Server.

Después de actualizar el archivo Web. config, debe ejecutar el comando siguiente en el servidor back-end de Exchange para reciclar el grupo de Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Si la operación de reciclaje se ejecuta correctamente, verá el siguiente mensaje en el shell de administración de Exchange:

    "MSExchangeOWAAppPool" successfully recycled

**Configurar las directivas de buzones de correo de Outlook Web App**

En este punto, puede usar el siguiente comando para configurar la mensajería instantánea en las directivas de buzones de correo de Outlook Web App adecuadas. Por ejemplo, al ejecutarlo en uno de los servidores de buzones de correo, este comando permite la mensajería instantánea en la directiva predeterminada:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Y este comando habilita la mensajería instantánea para todas las directivas de buzones de correo de Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Después de habilitar la Directiva de buzón, todos los usuarios administrados por esa Directiva tendrán la integración completa entre Lync Server y Outlook Web App, siempre y cuando:

  - El usuario tiene un buzón en Exchange 2013.

  - El usuario se ha habilitado para Lync Server 2013.

  - El usuario tenga una dirección de proxy SIP válida.

**Deshabilitar la mensajería instantánea en Outlook Web App**

Como se mencionó anteriormente, la mensajería instantánea está habilitada de manera predeterminada en Outlook Web App. Eso significa que, si no integra Outlook Web App con Lync Server, los usuarios verán los iconos de presencia en blanco y un mensaje de error cada vez que inicien sesión en Outlook Web App. Para evitar este problema, use el siguiente comando del shell de administración de Exchange para deshabilitar la mensajería instantánea en Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Comprobar la integración en Outlook Web App**

Para comprobar que la mensajería instantánea y la presencia se han integrado con Outlook Web App, inicie sesión en Outlook Web App 2013. En la esquina superior derecha de la pantalla, verá su nombre para mostrar de Exchange. Si hay un icono de presencia junto al nombre (por ejemplo, un icono verde que indica que está disponible el estado actual), significa que ha integrado correctamente Lync Server y Outlook Web App.

Cuando inicie sesión en Outlook Web App por primera vez, compruebe si se ha escrito un evento con el identificador de evento 112 (y el MSExchange OWA de origen) en el registro de eventos del servidor de buzones de correo. Este evento indica que el administrador de extremos de mensajería instantánea se inicializó correctamente. Si aparentemente no funciona la mensajería instantánea, en el servidor de buzones busque los archivos\\de registro en la carpeta C: archivos\\de programa Microsoft\\Exchange Server\\V15\\Logging\\OWA\\InstantMessaging. Si no existe la carpeta Logging o la carpeta InstantMessaging, significa que se produjo un error en la integración. En ese caso, puede usar el seguimiento SIPStack en Lync Server (todos los niveles y todos los indicadores) para intentar determinar por qué se produjo el error de integración.

</div>

<span> </span>

</div>

</div>

</div>

