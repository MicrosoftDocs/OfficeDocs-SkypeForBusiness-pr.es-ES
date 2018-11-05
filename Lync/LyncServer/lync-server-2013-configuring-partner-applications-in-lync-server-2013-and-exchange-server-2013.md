---
title: "Configurar aplicaciones de socio en MS Lync Server 2013 y MS Exchange Server 2013"
TOCTitle: "Conf. des app. partenaires dans MLS 2013 et MES 2013"
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49889401
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En la autenticación de servidor a servidor suelen participar tres entidades: los dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si dos servidores (por ejemplo, Servidor A y Servidor B) necesitan comunicarse entre sí, normalmente empezarán por ponerse en contacto con un servidor de tokens y obtener un token de seguridad que sea de confianza para ambos. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.

Ahora bien, eso no es sino una regla general. Lync Server 2013, Microsoft Exchange Server 2013 y Microsoft SharePoint Server 2013 no necesitan recurrir a un servidor de tokens de un tercero para comunicarse entre sí; eso se debe a que estos productos de servidor pueden crear tokens de seguridad que todos pueden aceptar sin necesidad de que haya un servidor de tokens aparte. (Esta capacidad solo está disponible en Lync Server 2013, Exchange 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).

Para configurar la autenticación de servidor a servidor entre Lync Server y Exchange, deberá hacer dos cosas: 1) asignar los certificados apropiados a cada servidor; y 2) configurar cada servidor como aplicación de socio del otro servidor: eso significa que debe configurar Lync Server 2013 como aplicación de socio para Exchange 2013 y Exchange 2013 como aplicación de socio para Lync Server 2013.

## Configurar Lync Server 2013 como aplicación de socio para Exchange 2013

La forma más fácil de configurar Lync Server 2013 como aplicación de socio con Exchange 2013 es ejecutar Configure-EnterprisePartnerApplication.ps1, un script de Windows PowerShell que se incluye con Exchange 2013. Para ejecutar este script, deberá facilitar la dirección URL del documento de metadatos de autenticación de Lync Server; normalmente, será el nombre de dominio completo del grupo de servidores de SharePoint seguido del sufijo /metadata/json/1. Por ejemplo:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Para configurar Lync Server como aplicación de socio, abra el Shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en la unidad C: y utilice la ruta de acceso a la carpeta predeterminada):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Tras configurar la aplicación de socio, se recomienda detener y reiniciar Internet Information Services (IIS) en sus servidores de acceso a cliente y buzón de Exchange. Puede reiniciar IIS usando un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:

    iisreset atl-exchange-001

Este comando puede ejecutarse desde dentro del Shell de administración de Exchange o desde cualquier otra ventana de comandos si se cuenta con privilegios de administrador.

## Configurar Exchange 2013 como aplicación de socio para Lync Server 2013

Tras configurar Lync Server 2013 como aplicación de socio para Exchange 2013, deberá configurar Exchange como aplicación de socio para Lync Server. Puede hacerlo utilizando el Shell de administración de Lync Server y especificando el documento de metadatos de autenticación de Exchange; normalmente será el URI del servicio de autodetección de Exchange seguido del sufijo /metadata/json/1. Por ejemplo:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

En Lync Server, las aplicaciones de socio se configuran utilizando el cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPartnerApplication). Además de especificar el URI de metadatos, también deberá establecer el nivel de confianza de la aplicación en Plena; de esta manera, Exchange podrá representarse a sí mismo y a cualquier usuario autorizado en el dominio. Por ejemplo:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Para crear una aplicación de socio también puede copiar y modificar el código de script que figura en la documentación sobre autenticación de servidor a servidor de Lync Server 2013. Para obtener más información, consulte el artículo [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

Si ha configurado correctamente aplicaciones de socios para Lync Server y Exchange, eso significará que también habrá configurado correctamente la autenticación de servidor a servidor entre los dos productos. Lync Server 2013 incluye [Test-CsExStorageConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExStorageConnectivity), un cmdlet de Windows PowerShell que le permite verificar si se ha configurado correctamente la autenticación de servidor a servidor y si el Servicio de almacenamiento de Lync Server puede conectar con Exchange 2013. Para ello, el cmdlet conecta con el buzón de un usuario de Exchange 2013 escribiendo un elemento en la carpeta Historial de conversaciones de dicho usuario y luego, de manera opcional, eliminando dicho elemento.

Para probar la integración de Lync Server 2013 y Exchange 2013, ejecute un comando similar a este desde dentro del Shell de administración de Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

En el comando anterior, el SipUri representa la dirección SIP de un usuario con una cuenta en Exchange 2013; el comando dará error en ese punto si la cuenta de usuario no es válida.

Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.

