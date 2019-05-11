---
title: Configuración de las aplicaciones asociadas en Skype para Business Server 2015 y Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumen: Configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.'
ms.openlocfilehash: 70433d0a6f3b6d9c30e510e116003a4efb5ba9b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894340"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configuración de las aplicaciones asociadas en Skype para Business Server y Exchange Server
 
**Resumen:** Configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.
  
En la autenticación de servidor a servidor suelen participar dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si necesitan comunicarse servidores A y B, a continuación, ambos de esos servidores normalmente empezar por ponerse en contacto con un servidor de token y cómo obtener un token de seguridad de confianza mutuamente. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.
  
Ahora bien, eso no es sino una regla general. No es necesario usar un servidor de símbolo (token) de otro fabricante al comunicarse con otro; Skype para Business Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013 que es debido a que estos productos de servidor pueden crear tokens de seguridad que pueden aceptarse por uno a otro sin necesidad de un servidor independiente de símbolo (token). (Esta función sólo está disponible en Skype para Business Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).
  
Con el fin de configurar la autenticación de servidor a servidor entre Skype para Business Server y Exchange Server debe hacer dos cosas: 1) debe asignar los certificados apropiados a cada servidor; y, 2) debe configurar cada servidor para que sea una aplicación de socio del otro servidor: significa que debe configurar Skype para Business Server como una aplicación de socio para Exchange Server, y debe configurar Exchange Server para que sea una aplicación de socio de Skype para Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configuración de Skype para Business Server como una aplicación de socio para Exchange Server

Es la forma más sencilla de configurar Skype para Business Server como una aplicación de socio con Exchange Server 2016 o Exchange Server 2013 ejecutar el script Configure-EnterprisePartnerApplication.ps1, una secuencia de comandos de Windows PowerShell que se incluye con Exchange Server. Para ejecutar este script, debe proporcionar la dirección URL para el Skype para el documento de metadatos de autenticación de servidor empresarial; Normalmente, se trata del nombre de dominio completo de la Skype para grupo de servidores de negocio seguido por el sufijo /metadata/json/1. Por ejemplo:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar Skype para Business Server como una aplicación de socio, abra el Shell de administración de Exchange y ejecute un comando similar al siguiente (suponiendo que se ha instalado Exchange en la unidad C: y que TI utiliza la ruta de acceso de la carpeta predeterminada):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Después de configurar la aplicación de socio, se recomienda que detenga y reinicie Internet Information Services (IIS) en los servidores de acceso de cliente y buzón de correo de Exchange. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde dentro de la consola de administración de Exchange o desde cualquier otra ventana de comandos que se ejecute con privilegios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuración de Exchange Server como una aplicación de socio para Skype para Business Server

Una vez haya configurado Skype para Business Server como una aplicación de socio para Exchange Server 2016 o Exchange Server 2013, a continuación, debe configurar Exchange Server para que sea una aplicación de socio para Skype para Business Server. Esto puede realizarse mediante el Skype para Shell de administración de servidor empresarial y especifique el documento de metadatos de autenticación para Exchange; Normalmente será el URI del servicio de detección automática de Exchange seguido por el sufijo /metadata/json/1. Por ejemplo:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

En Skype para Business Server, se configuran las aplicaciones asociadas con el cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Además de especificar el URI de metadatos también debe establecer la confianza de la aplicación nivel en completo; Esto le permitirá Exchange representar propio y cualquier usuario autorizado en el dominio. Por ejemplo:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, puede crear una aplicación de socio copiando y modificando el código de secuencia de comandos que se encuentran en el Skype para la documentación de autenticación de servidor a servidor Business Server. Vea el artículo [Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) para obtener más información.
  
Si ha configurado correctamente las aplicaciones asociadas para ambos Skype para Business Server y Exchange Server, se configuró correctamente también autenticación de servidor a servidor entre los dos productos. Skype para Business Server incluye un cmdlet de Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que le permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que puede el Skype para servicio de almacenamiento de información de servidor empresarial Conéctese al servidor de Exchange. El cmdlet lo hace mediante la conexión al buzón de un usuario de Exchange Server, escribir un elemento en la carpeta Historial de conversaciones para que el usuario y, a continuación, eliminación (opcionalmente) de ese elemento.
  
Para probar la integración de Skype para Business Server y Exchange Server, ejecute un comando similar a los siguientes elementos desde el Skype para Shell de administración de servidor empresarial:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

En el comando anterior, el SipUri representa la dirección SIP de un usuario con una cuenta en el servidor de Exchange; el comando se producirá un error en esto no es una cuenta de usuario válido.
  
> [!NOTE]
> Si se recibe una respuesta 401 de este cmdlet, probablemente es debido a que la configuración predeterminada de Exchange no incluye compatibilidad para aceptar los tokens de Oauth. Para obtener más información acerca del uso de Oauth en Exchange, vea [autenticación de OAuth configurar con SharePoint 2013 y Skype para Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.
