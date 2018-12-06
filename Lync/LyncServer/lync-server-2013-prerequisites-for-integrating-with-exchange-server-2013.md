---
title: "Requisitos previos para integración de MS Lync Server 2013 y MS Exchange Server 2013"
TOCTitle: "Configuration requise pour l’intégration de MLS 2013 et MES 2013"
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49889793
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos para la integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Antes de poder integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, debe asegurarse de que se han llevado a cabo todos los pasos previos necesarios. Como puede imaginar, la integración no podrá realizarse hasta que Exchange 2013 y Lync Server 2013 estén completamente instalados y en funcionamiento. Si desea información detallada sobre la instalación de Exchange, consulte la documentación de Planificación e implementación de Exchange 2013 en [http://go.microsoft.com/fwlink/?linkid=268539\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268539%26clcid=0xc0a). Si desea información detallada sobre la instalación de Lync Server 2013, consulte la documentación Planificación e implementación en [http://go.microsoft.com/fwlink/?linkid=254806\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=254806%26clcid=0xc0a).

Después de tener varios servidores en funcionamiento, tendrá que asignar certificados de autenticación de servidor a servidor tanto a Lync Server 2013 como a Exchange 2013; estos certificados permiten a Lync Server y Exchange intercambiar información y comunicarse entre sí. Cuando instale Exchange 2013, se creará un certificado autofirmado con el nombre Microsoft Exchange Server Auth Certificate. Este certificado, que se puede encontrar en el almacén de certificados del equipo local, se deberá utilizar para la autenticación de servidor a servidor en Exchange 2013. Si desea información detallada sobre la asignación de certificados en Exchange 2013, consulte Configuración de flujo de correo y acceso de cliente, en [http://go.microsoft.com/fwlink/?linkid=268540\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268540%26clcid=0xc0a).

Para Lync Server 2013, puede utilizar un certificado Lync Server existente como certificado de autenticación de servidor a servidor. Por ejemplo, también puede usar su certificado predeterminado como certificado OAuthTokenIssuer. Lync Server 2013 le permite utilizar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor siempre que:

  - El certificado incluya el nombre del dominio SIP en el campo Asunto.

  - Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.

  - El certificado tenga una longitud de al menos 2048 bits.

Si desea información detallada sobre los certificados de autenticación de servidor a servidor para Microsoft Lync Server 2013, consulte [Asignación de un certificado de autenticación servidor a servidor a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Después de haber asignado los certificados, deberá configurar el Servicio de detección automática en Exchange 2013. En Exchange 2013, el servicio de detección automática configura los perfiles de usuario y ofrece acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios facilitan al servicio de detección automática su dirección de correo electrónico y su contraseña. A cambio, los servicios ofrecen al usuario información como:

  - Información de conexión sobre la conectividad interna y la externa con Exchange 2013.

  - La ubicación del servidor de Buzón de correo del usuario.

  - Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.

  - Configuración del servidor Outlook Anywhere.

El servicio de detección automática debe configurarse antes de integrar Lync Server 2013 y Exchange 2013. Para comprobar si el servicio de detección automática ha sido o no configurado, ejecute el comando siguiente desde el Shell de administración de Exchange y compruebe el valor de la propiedad AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Por lo general, este URI será similar al siguiente:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Para obtener más información sobre el servicio de detección automática, consulte "Descripción del servicio de detección automática" en [http://go.microsoft.com/fwlink/?linkid=268542\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268542%26clcid=0xc0a).

Después de configurar el servicio de detección automática, deberá modificar las opciones de configuración de OAuth de Lync Server. De este modo, Lync Server sabrá dónde encontrar el servicio de detección automática. Para modificar las opciones de configuración de OAuth en Lync Server 2013, ejecute el siguiente comando desde dentro de Shell de administración de Lync Server. Al ejecutar este comando, asegúrese de que especifica el URI al servicio de detección automática que se ejecuta en su servidor Exchange y que utiliza **autodiscover.svc** para especificar la ubicación del servicio, y no **autodiscover.xml** (que especifica el archivo XML que usa el servicio):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc


> [!NOTE]
> El parámetro Identity del comando anterior es opcional ya que Lync Server solo permite tener una colección única global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple:<BR>Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto.



Además de configurar el servicio de detección automática, debe crear un registro de DNS para el servicio que hace referencia a su servidor Exchange. Por ejemplo, si su servicio de detección automática está ubicado en autodiscover.litwareinc.com, tendrá que crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo de su servidor Exchange (por ejemplo, atl-exchange-001.litwareinc.com).

