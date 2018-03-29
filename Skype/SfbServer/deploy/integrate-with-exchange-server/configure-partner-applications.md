---
title: Configurar aplicaciones de socios en Skype para 2015 de Business Server y Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumen: Configurar la autenticación de servidor a servidor de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: d7b3d93126c5b2db06e5f7343f5636b3c305d7c8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-partner-applications-in-skype-for-business-server-2015-and-exchange-server"></a>Configurar aplicaciones de socios en Skype para 2015 de Business Server y Exchange Server
 
**Resumen:** Configurar la autenticación de servidor a servidor de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.
  
En la autenticación de servidor a servidor suelen participar dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si necesitan comunicarse servidores A y B, ambos de dichos servidores normalmente inícielo de ponerse en contacto con un servidor testigo y obteniendo un token de seguridad de confianza mutua. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.
  
Ahora bien, eso no es sino una regla general. Skype para Business Server 2015, 2016 de Exchange Server, Exchange Server 2013 y 2013 de servidor de SharePoint no es necesario utilizar un servidor de símbolo (token) de otros fabricantes cuando se comunica con otro; eso es porque estos productos del servidor pueden crear tokens de seguridad que pueden aceptarse entre sí sin necesidad de un servidor independiente de símbolo (token). (Esta función sólo está disponible en Skype para Business Server 2015, 2016 de Exchange Server, Exchange Server 2013 y 2013 de SharePoint Server. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).
  
Para configurar la autenticación de servidor a servidor entre Skype para Business Server y Exchange Server debe hacer dos cosas: 1) debe asignar los certificados apropiados a cada servidor; y, 2) debe configurar cada servidor para que sea una aplicación asociada del otro servidor: significa que debe configurar Skype para Business Server 2015 por una aplicación de socios para Exchange Server y debe configurar Exchange Server para que sea una aplicación asociada para Skype para Business Server 2015.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurar Skype para Business Server sea una aplicación asociada para Exchange Server

La forma más sencilla de configurar Skype para Business Server 2015 sea una aplicación asociada con 2016 de Exchange Server o Exchange Server 2013 es ejecutar la secuencia de comandos de EnterprisePartnerApplication.ps1 de configurar, una secuencia de comandos de Windows PowerShell que se incluye con Exchange Server . Para ejecutar esta secuencia de comandos, debe proporcionar la dirección URL para el Skype para el documento de metadatos de Business Server autenticación; Normalmente se trata del nombre de dominio completo de la Skype para grupo Business Server 2015 seguido por el sufijo /metadata/json/1. Por ejemplo:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar Skype para Business Server como una aplicación de socio, abra el Shell de administración de Exchange y ejecutar un comando similar al siguiente (suponiendo que se ha instalado Exchange en la unidad C: y que TI utiliza la ruta de la carpeta predeterminada):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Se recomienda que detenga y reinicie Servicios de Internet Information Server (IIS) en los servidores de acceso de cliente y buzón de correo de Exchange después de configurar la aplicación asociada. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde el Shell de administración de Exchange o desde cualquier otra ventana de comando ejecutar con privilegios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Cómo configurar Exchange Server para una solicitud de socio de Skype para Business Server

Después de haber configurado Skype para Business Server 2015 para una solicitud de socio de 2016 de Exchange Server o Exchange Server 2013, a continuación, debe configurar Exchange Server para que sea una aplicación asociada para Skype para Business Server. Esto puede hacerse usando el Skype para el Shell de administración de servidor empresarial y especificando el documento de metadatos de autenticación para Exchange; Normalmente será el URI del servicio de detección automática de Exchange, seguido por el sufijo /metadata/json/1. Por ejemplo:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

En Skype para Business Server, aplicaciones de los socios se configuran mediante el cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Además de especificar los metadatos URI debe también establecer la confianza de la aplicación nivel al completo; Esto permitirá el intercambio representar a sí mismo y cualquier usuario autorizado en el territorio. Por ejemplo:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, puede crear una aplicación de socio copiando y modificando el código de secuencia de comandos se encuentra en el Skype para la documentación de autenticación de servidor a servidor Business Server 2015. Vea el artículo [Administrar la autenticación de servidor a servidor (OAuth) y aplicaciones de los socios en Skype para Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md) para obtener más información.
  
Si ha configurado correctamente las aplicaciones de socios para ambos Skype para Business Server y Exchange Server, también ha haber configurado la autenticación de servidor a servidor entre los dos productos. Skype para Business Server 2015 incluye un cmdlet de Windows PowerShell, [CsExStorageConnectivity de prueba](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , lo que permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el Skype para el servicio de almacenamiento de información de Business Server puede conectarse a Exchange Server. Para ello, el cmdlet conectarse al buzón de un usuario de Exchange Server, escribir un artículo en la carpeta Historial de las conversaciones para ese usuario y (opcionalmente) eliminar ese elemento.
  
Para probar la integración de Skype for Business Server 2015 y Exchange Server, ejecute un comando similar al siguiente en el Skype para el Shell de administración de servidor de negocios:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

En el comando anterior, el SipUri representa la dirección SIP de un usuario con una cuenta en Exchange Server; el comando producirá un error en esto no es una cuenta de usuario válida.
  
> [!NOTE]
> Si recibes una respuesta 401 de este cmdlet, probablemente es porque la configuración predeterminada de Exchange no incluye compatibilidad para la aceptación de símbolos (tokens) de Oauth. Para obtener más información acerca de cómo utilizar Oauth en Exchange, vea [autenticación de OAuth configurar con SharePoint 2013 y Skype para Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.
  

