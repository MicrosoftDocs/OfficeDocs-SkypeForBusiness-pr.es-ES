---
title: Configurar aplicaciones de socios en Lync Server 2013 y Exchange Server 2013
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
ms.openlocfilehash: c60e018a86ec0838791d5fc46845460b5f039f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configurar aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

Normalmente, la autenticación de servidor a servidor implica tres entidades: los dos servidores que necesitan comunicarse entre sí y un servidor de token de seguridad de terceros. Si dos servidores necesitan comunicarse (por ejemplo, el servidor A y el servidor B), ambos servidores suelen empezar poniéndose en contacto con un servidor de tokens y obtienen un token de seguridad mutuamente confiable. A continuación, el servidor a presenta ese token de seguridad al servidor B (y viceversa) como una forma de garantizar su autenticidad y su grado de confianza.

Ahora bien, eso no es sino una regla general. Lync Server 2013, Microsoft Exchange Server 2013 y Microsoft SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros cuando se comunican entre sí; Esto se debe a que estos productos de servidor pueden crear tokens de seguridad que se pueden aceptar entre sí sin necesidad de un servidor de token independiente. (Esta característica solo está disponible en Lync Server 2013, Exchange 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).

Para configurar la autenticación de servidor a servidor entre Lync Server y Exchange, debe hacer dos cosas: 1) debe asignar los certificados adecuados a cada servidor. y 2) debe configurar cada servidor para que sea una aplicación asociada al otro servidor: Esto significa que debe configurar Lync Server 2013 como una aplicación asociada para Exchange 2013, y debe configurar Exchange 2013 como una aplicación asociada para Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configuración de Lync Server 2013 como una aplicación de socio para Exchange 2013

La forma más sencilla de configurar Lync Server 2013 como una aplicación de socio con Exchange 2013 es ejecutar el script Configure-EnterprisePartnerApplication. ps1, un script de Windows PowerShell que se incluye con Exchange 2013. Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos de autenticación de Lync Server; normalmente será el nombre de dominio completo del grupo de 2013 de Lync Server, seguido del sufijo/Metadata/JSON/1. Por ejemplo:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Para configurar Lync Server como aplicación de socio, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en el disco C: y que use la ruta de la carpeta predeterminada):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Después de configurar la aplicación de socio, se recomienda que detenga y reinicie servicios de Internet Information Server (IIS) en el buzón de Exchange y en los servidores de acceso de cliente. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:

    iisreset atl-exchange-001

Este comando se puede ejecutar desde el shell de administración de Exchange o desde cualquier otra ventana de comandos con privilegios de administrador.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configuración de Exchange 2013 como una aplicación asociada para Lync Server 2013

Una vez que haya configurado Lync Server 2013 para que sea una aplicación de socio para Exchange 2013, debe configurar Exchange para que sea una aplicación de Partner para Lync Server. Esto se puede hacer con el shell de administración de Lync Server y especificar el documento de metadatos de autenticación para Exchange. normalmente será el URI del servicio Detección automática de Exchange, seguido del sufijo/Metadata/JSON/1. Por ejemplo:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

En Lync Server, las aplicaciones asociadas se configuran mediante el cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) . Además de especificar el URI de los metadatos, también debe establecer el nivel de confianza de la aplicación en completo; Esto permitirá a Exchange representar tanto a sí mismo como a cualquier usuario autorizado en el territorio. Por ejemplo:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Como alternativa, puede crear una aplicación de socio copiando y modificando el código de script que se encuentra en la documentación de autenticación de servidor a servidor de Lync Server 2013. Para obtener más información, vea el artículo administración de la [autenticación de servidor a servidor (OAuth) y aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Si ha configurado correctamente aplicaciones de socio tanto para Lync Server como para Exchange, significa que también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos. Lync Server 2013 incluye un cmdlet de Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), que le permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio de almacenamiento de Lync Server puede conectarse a Exchange 2013. El cmdlet realiza esta acción conectándose al buzón de un usuario de Exchange 2013, escribiendo un elemento en la carpeta Historial de conversaciones para ese usuario y, a continuación, también puede eliminarlo.

Para probar la integración de Lync Server 2013 y Exchange 2013, ejecute un comando similar a este en el shell de administración de Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

En el comando anterior, SipUri representa la dirección SIP de un usuario con una cuenta en Exchange 2013; el comando fallará en esta no es una cuenta de usuario válida.

Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

