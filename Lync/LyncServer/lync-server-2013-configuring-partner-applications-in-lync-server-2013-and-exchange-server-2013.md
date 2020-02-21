---
title: Configuración de aplicaciones de socio en Lync Server 2013 y Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

En la autenticación de servidor a servidor suelen participar tres entidades: los dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si dos servidores (por ejemplo, Servidor A y Servidor B) necesitan comunicarse entre sí, normalmente empezarán por ponerse en contacto con un servidor de tokens y obtener un token de seguridad que sea de confianza para ambos. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.

Ahora bien, eso no es sino una regla general. Lync Server 2013, Microsoft Exchange Server 2013 y Microsoft SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros para comunicarse entre sí; Esto se debe a que estos productos de servidor pueden crear tokens de seguridad que puedan aceptarse entre sí sin necesidad de un servidor de token independiente. (Esta funcionalidad solo está disponible en Lync Server 2013, Exchange 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).

Para configurar la autenticación de servidor a servidor entre Lync Server y Exchange, debe hacer dos cosas: 1) debe asignar los certificados apropiados a cada servidor; y 2) debe configurar cada servidor para que sea una aplicación de socio del otro servidor: Esto significa que debe configurar Lync Server 2013 como una aplicación de socio para Exchange 2013, y debe configurar Exchange 2013 como una aplicación de socio para Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configuración de Lync Server 2013 como una aplicación de socio para Exchange 2013

La forma más sencilla de configurar Lync Server 2013 como una aplicación de socio con Exchange 2013 es ejecutar el script configure-enterprisepartnerapplication. ps1, un script de Windows PowerShell que se incluye con Exchange 2013. Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos de autenticación de Lync Server; normalmente será el nombre de dominio completo del grupo de servidores de Lync Server 2013 seguido del sufijo/Metadata/JSON/1. Por ejemplo:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Para configurar Lync Server como una aplicación de socio, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en la unidad C: y que use la ruta de acceso a la carpeta predeterminada):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Después de configurar la aplicación de socio, se recomienda que detenga y reinicie Internet Information Services (IIS) en los servidores de buzones de correo y de acceso de cliente de Exchange. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:

    iisreset atl-exchange-001

Este comando se puede ejecutar desde dentro del shell de administración de Exchange o desde cualquier otra ventana de comandos que se ejecute con privilegios de administrador.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configuración de Exchange 2013 como una aplicación de socio para Lync Server 2013

Una vez que haya configurado Lync Server 2013 como una aplicación de socio para Exchange 2013, debe configurar Exchange para que sea una aplicación de socio para Lync Server. Esto puede realizarse mediante el shell de administración de Lync Server y especificando el documento de metadatos de autenticación para Exchange; normalmente será el URI del servicio Detección automática de Exchange seguido del sufijo/Metadata/JSON/1. Por ejemplo:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

En Lync Server, las aplicaciones asociadas se configuran con el cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) . Además de especificar el URI de metadatos, también debe establecer el nivel de confianza de la aplicación en completo; Esto permitirá que Exchange represente tanto a los usuarios autorizados como a los autorizados en el dominio Kerberos. Por ejemplo:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Como alternativa, puede crear una aplicación de socio copiando y modificando el código de script que se encuentra en la documentación de autenticación de servidor a servidor de Lync Server 2013. Vea el artículo [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) para obtener más información.

Si ha configurado correctamente aplicaciones de socio tanto para Lync Server como para Exchange, significa que también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos. Lync Server 2013 incluye un cmdlet de Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), que permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio de almacenamiento de Lync Server puede conectarse a Exchange 2013. Para ello, se conecta al buzón de un usuario de Exchange 2013, escribe un elemento en la carpeta Historial de conversaciones de ese usuario y, a continuación, elimina el elemento de la manera siguiente.

Para probar la integración de Lync Server 2013 y Exchange 2013, ejecute un comando similar a este desde dentro del shell de administración de Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

En el comando anterior, SipUri representa la dirección SIP de un usuario con una cuenta en Exchange 2013; el comando no se completará en esta cuenta de usuario no es válida.

Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

