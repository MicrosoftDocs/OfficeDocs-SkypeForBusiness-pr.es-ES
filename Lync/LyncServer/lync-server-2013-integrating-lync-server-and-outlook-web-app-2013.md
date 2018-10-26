---
title: Integrar Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013
TOCTitle: Integrar Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49889083
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integrar Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013

 

_**Última modificación del tema:** 2016-12-08_

Además de la integración con Microsoft Outlook 2013, Microsoft Lync Server 2013 puede integrarse completamente con Microsoft Outlook Web App 2013. Entre otras cosas, esto agrega mensajería instantánea y presencia para Outlook Web App y permite que la lista de contactos unificada se comparta entre Outlook Web App y Microsoft Lync 2013. Para integrar Lync Server 2013 y Outlook Web App, primero debe comprobar que se haya instalado la API administrada de comunicaciones unificadas 4.0 Runtime en el servidor back-end de Microsoft Exchange Server 2013. Puede hacerlo buscando si existe el siguiente valor del Registro:

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath debe apuntar a la ubicación de la carpeta del archivo Microsoft.Rtc.Internal.Ucweb.dll. Si no lo hace, o si el valor del Registro no existe, debe descargar e instalar el programa de instalación UCMA Runtime desde el Centro de descarga de Microsoft en <http://www.microsoft.com/es-es/download/details.aspx?id=34992>. En la misma página web, encontrará información sobre cómo instalar UCMA Runtime.

**Compatibilidad con versiones anteriores**

Lync Server 2013 se puede integrar con las versiones de Microsoft Exchange Server 2010 tanto de mensajería unificada como de Outlook Web App. Para obtener más información, consulte el artículo Implementación de la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2010 en [http://technet.microsoft.com/es-es/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md). Si se integra con Exchange 2010, no dispondrá de las características específicas de Lync Server, como el almacén de contactos unificado y el archivado de Lync a Exchange.

Microsoft Lync 2013 también se puede usar junto con Exchange 2010 y Outlook 2010. Sin embargo, como se mencionó anteriormente, no estará disponible para los usuarios de Lync 2013 la funcionalidad nueva, como el almacén de contactos unificado y las fotos de alta resolución. Estas funcionalidades nuevas requieren tanto Lync Server 2013 como Exchange 2013.

**Creación de un grupo de aplicaciones de confianza para Outlook Web App**

Si ha instalado el servicio de enrutador de llamadas de mensajería unificada de Microsoft Exchange y el servicio de mensajería unificada de Microsoft Exchange en el mismo equipo, no hay necesidad de crear un grupo de aplicaciones de confianza para Outlook Web App. (Se supone que el servidor en cuestión hospeda un plan de marcado de MU SipName). Si usa un solo equipo para hospedar ambos servicios, puede saltar a la sección **Habilitar la mensajería instantánea en Outlook Web App** de este documento.

Lync Server 2013 puede detectar automáticamente cualquier servidor de Exchange que hospede un plan de marcado de MU SipName. Estos servidores se agregan automáticamente a la lista de servidores conocidos de Lync Server. No hay necesidad de crear un grupo de aplicaciones de confianza ni de agregar estos servidores a la lista de servidores conocidos. De hecho, si lo hace, la integración con Outlook Web App dejará de funcionar.


> [!NOTE]
> Esto se debe a que la topología de Lync Server ahora tendrá dos entradas para el mismo equipo: la entrada detectada automáticamente y la entrada agregada de forma manual. Para corregir el problema y lograr que Outlook Web App vuelva a funcionar, use Windows PowerShell para quitar las entradas del grupo de confianza y de la aplicación de confianza para el servidor. Consulte los temas de Ayuda acerca de los cmdlets <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> y <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obtener más información.



Si estos dos servicios se ejecutan en equipos independientes, después de haber comprobado que se ha instalado la API administrada de comunicaciones unificadas 4.0 Runtime, debe crear un grupo de aplicaciones de confianza de Lync Server y una aplicación de confianza asociada con Outlook Web App, lo que agregará el servidor a la lista de servidores conocidos. Para ello, primero ejecute un comando similar a este desde el Shell de administración de Lync Server:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

En el comando anterior, atl-owa-001.litwareinc.com es el nombre de dominio completo del grupo de Outlook Web App. Debe ser el mismo nombre que aparece en los campos Nombre del sujeto y Nombre alternativo del sujeto del certificado que proporciona acceso a Outlook Web App. Asimismo, atl-cs-001.litwareinc.com es el nombre de dominio completo del grupo de Lync Server 2013 que hospedará el nuevo grupo de aplicaciones de confianza. Tenga en cuenta también que el sitio especificado, Redmond, representa el SiteID del sitio de Lync Server. El SiteID no es necesariamente el mismo que el DisplayName del sitio; puede recuperar los SiteID de los sitios de Lync Server si ejecuta el siguiente comando desde el Shell de administración de Lync Server:

    Get-CsSite | Select-Object DisplayName, SiteID

Después de crear el grupo de aplicaciones de confianza, use un comando similar al siguiente para configurar una identidad de aplicación y un puerto para Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

En el comando anterior, ApplicationID simplemente es un identificador fácil de usar usado para distinguir las aplicaciones de confianza. ApplicationID puede ser cualquier cadena de texto que no incluya espacios en blanco u otros caracteres prohibidos. (Para garantizar la creación de un identificador válido, se recomienda que use solo letras y números al especificar un ApplicationID). El valor asignado al parámetro Port también queda a discreción del administrador: puede ser cualquier puerto disponible de la red.

Después de crear la aplicación de confianza, debe ejecutar el siguiente comando para habilitar los cambios en la topología de Lync Server:

    Enable-CsTopology

Tenga en cuenta que también debe agregar el servidor de buzones de correo y acceso de cliente de Exchange a todos sus planes de marcado URI de SIP. A su vez, esto configurará los servidores como pares SIP de confianza con la topología ExUmRouting para Lync Server.

**Habilitar la mensajería instantánea en Outlook Web App**

Con Lync Server correctamente configurado, puede empezar a configurar Outlook Web App. El primer paso de ese proceso es habilitar la mensajería instantánea en todos los directorios virtuales de Outlook Web App de sus servidores front-end. (No es necesario habilitar la mensajería instantánea para los directorios virtuales de los servidores back-end. De hecho, se recomienda no habilitar la mensajería instantánea en estos servidores). La mensajería instantánea se puede habilitar en los servidores de acceso de cliente ejecutando el siguiente comando desde el Shell de administración de Exchange:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS


> [!NOTE]
> De manera predeterminada, la mensajería instantánea se habilita al instalar Outlook Web App; es decir, la propiedad InstantMessagingEnabled se establece en True. Sin embargo, aún debe ejecutar el comando anterior para establecer el tipo de mensajería instantánea en OCS. De manera predeterminada, InstantMessagingType está establecido en None.



A continuación, debe agregar las siguientes líneas al archivo Web.config de Outlook Web App (este archivo normalmente se encuentra en la carpeta C:\\Archivos de programa\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa). Estas dos líneas deben agregarse en el nodo \<AppSettings\> del archivo Web.config y este procedimiento debe llevarse a cabo solo en los servidores back-end en los que se ha instalado Outlook Web App:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

En el ejemplo anterior, el valor de IMCertificateThumbprint debe ser la huella digital del certificado de Exchange 2013 instalado en los servidores back-end. Puede recuperar esa información si ejecuta el siguiente comando desde el Shell de administración de Exchange:

    Get-ExchangeCertificate

Tenga en cuenta también que el valor asignado a IMServerName es el nombre de dominio completo del grupo de Lync Server donde creó el grupo de aplicaciones de confianza para Outlook Web App.

El certificado que use para Outlook Web App debe ser de confianza para Lync Server. Un modo de cerciorarse de que el certificado será de confianza tanto para Lync Server como para Exchange consiste en usar la entidad de certificación interna para crear un certificado en el servidor de buzones de correo, asegurándose de que se use el FQDN del servidor como nombre del sujeto y este FQDN aparezca en el campo de nombre alternativo del certificado. Una vez creado el certificado, puede importarse a los servidores back-end. El resultado final es que se usa el mismo certificado con dos fines: 1) la comunicación entre la mensajería unificada de Exchange y Lync Server, y 2) la integración entre Outlook Web App y Lync Server.

Después de haber actualizado el archivo Web.config, debe ejecutar el siguiente comando en el servidor back-end de Exchange para reciclar el grupo de Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Si la operación de reciclaje es correcta se verá el siguiente mensaje en el Shell de administración de Exchange:

    "MSExchangeOWAAppPool" successfully recycled

**Configurar las directivas de buzones de correo de Outlook Web App**

En este punto, puede usar el siguiente comando para configurar la mensajería instantánea en las directivas de buzones de correo de Outlook Web App adecuadas. Por ejemplo, al ejecutarlo en uno de los servidores de buzones de correo, este comando permite la mensajería instantánea en la directiva predeterminada:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Y este comando habilita la mensajería instantánea para todas las directivas de buzones de correo de Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Después de haber habilitado la directiva de buzones de correo, todos los usuarios administrados por esa directiva tendrán una integración completa entre Lync Server y Outlook Web App, siempre que:

  - El usuario tenga un buzón en Exchange 2013.

  - El usuario se haya habilitado para Lync Server 2013.

  - El usuario tiene una dirección de proxy SIP válida.

**Deshabilitar la mensajería instantánea en Outlook Web App**

Como se mencionó anteriormente, la mensajería instantánea está habilitada de manera predeterminada en Outlook Web App. Esto significa que, si no integra Outlook Web App con Lync Server, los usuarios verán iconos de presencia vacíos y un mensaje de error cada vez que inicien sesión en Outlook Web App. Para evitar este problema, use el siguiente comando del Shell de administración de Exchange para deshabilitar la mensajería instantánea en Outlook web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Comprobar la integración en Outlook Web App**

Para comprobar que la mensajería instantánea y la presencia se han integrado con Outlook Web App, inicie sesión en Outlook Web App 2013. En la esquina superior derecha de la pantalla, verá su nombre para mostrar de Exchange. Si aparece un icono de presencia junto a su nombre (por ejemplo, un icono verde que indica que su estado actual es Disponible), significa que ha integrado Lync Server y Outlook Web App correctamente.

Cuando inicie sesión en Outlook Web App por primera vez, compruebe si se ha escrito un evento con el identificador de evento 112 (y el MSExchange OWA de origen) en el registro de eventos del servidor de buzones de correo. Este evento indica que el administrador de extremos de mensajería instantánea se inicializó correctamente. Si la mensajería instantánea no parece funcionar, en el servidor de buzones de correo, busque los archivos de registro en la carpeta C:\\Archivos de programa\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging. Si no existe la carpeta Logging o la carpeta InstantMessaging, significa que se produjo un error en la integración. En ese caso, puede usar el seguimiento de SIPStack en Lync Server (Todos los niveles y Todas las marcas) para intentar determinar el motivo del error de la integración.

