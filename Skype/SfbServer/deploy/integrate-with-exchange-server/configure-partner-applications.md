---
title: Configurar aplicaciones de socio en Skype empresarial Server 2015 y Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumen: configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.'
ms.openlocfilehash: 4c7c8a0efb2432403422e33140c1a2fdf3551dd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306737"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicaciones de socio en Skype empresarial Server y Exchange Server
 
**Resumen:** Configure la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.
  
En la autenticación de servidor a servidor suelen participar dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si el servidor A y el servidor B necesitan comunicarse, ambos servidores suelen empezar poniéndose en contacto con un servidor de tokens y obtienen un token de seguridad mutuamente confiable. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.
  
Ahora bien, eso no es sino una regla general. Skype empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros cuando se comunican entre sí; Esto se debe a que estos productos de servidor pueden crear tokens de seguridad que se pueden aceptar entre sí sin necesidad de un servidor de token independiente. (Esta característica solo está disponible en Skype empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).
  
Para configurar la autenticación de servidor a servidor entre Skype empresarial Server y Exchange Server, debe hacer dos cosas: 1) debe asignar los certificados adecuados a cada servidor. y 2) debe configurar cada servidor para que sea una aplicación asociada al otro servidor, lo que significa que debe configurar Skype empresarial Server para que sea una aplicación de socio de Exchange Server y debe configurar Exchange Server como una aplicación de socio para Skype. para Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurar Skype empresarial Server para que sea una aplicación de socio para Exchange Server

La forma más sencilla de configurar Skype empresarial Server para que sea una aplicación de socio con Exchange Server 2016 o Exchange Server 2013 es ejecutar el script Configure-EnterprisePartnerApplication. ps1, un script de Windows PowerShell que se incluye con Exchange Server. Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos de autenticación de Skype empresarial Server. normalmente será el nombre de dominio completo del grupo de servidores de Skype empresarial, seguido del sufijo/Metadata/JSON/1. Por ejemplo:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar Skype empresarial Server como aplicación de socio, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en el disco C: y que use la ruta de la carpeta predeterminada):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Después de configurar la aplicación de socio, se recomienda que detenga y reinicie servicios de Internet Information Server (IIS) en el buzón de Exchange y en los servidores de acceso de cliente. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde el shell de administración de Exchange o desde cualquier otra ventana de comandos con privilegios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurar Exchange Server para que sea una aplicación de socio de Skype empresarial Server

Una vez que haya configurado Skype empresarial Server para que sea una aplicación de socio para Exchange Server 2016 o Exchange Server 2013, debe configurar Exchange Server para que sea una aplicación de socio de Skype empresarial Server. Esto se puede hacer con el shell de administración de Skype empresarial Server y especificar el documento de metadatos de autenticación para Exchange. normalmente será el URI del servicio Detección automática de Exchange, seguido del sufijo/Metadata/JSON/1. Por ejemplo:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

En Skype empresarial Server, las aplicaciones de socios se configuran mediante el cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Además de especificar el URI de los metadatos, también debe establecer el nivel de confianza de la aplicación en completo; Esto permitirá a Exchange representar tanto a sí mismo como a cualquier usuario autorizado en el territorio. Por ejemplo:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, puede crear una aplicación de socio copiando y modificando el código de script que se encuentra en la documentación de autenticación de servidor a servidor de Skype empresarial Server. Para obtener más información, consulte [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de asociados en el artículo de Skype empresarial Server](../../manage/authentication/server-to-server-and-partner-applications.md) .
  
Si ha configurado correctamente aplicaciones de socio para Skype empresarial Server y Exchange Server, también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos. Skype empresarial Server incluye un cmdlet de Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , que le permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio de almacenamiento de Skype empresarial Server puede conectarse al servidor de Exchange. El cmdlet realiza esta acción conectándose al buzón de un usuario de Exchange Server, escribiendo un elemento en la carpeta Historial de conversaciones de ese usuario y, a continuación (opcionalmente), eliminando ese elemento.
  
Para probar la integración de Skype empresarial Server y Exchange Server, ejecute un comando similar al siguiente en el shell de administración de Skype empresarial Server:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

En el comando anterior, SipUri representa la dirección SIP de un usuario con una cuenta en Exchange Server. el comando fallará en esta no es una cuenta de usuario válida.
  
> [!NOTE]
> Si recibe una respuesta 401 de este cmdlet, probablemente se deba a que la configuración predeterminada de Exchange no incluye compatibilidad para aceptar tokens de OAuth. Para obtener más información sobre cómo usar OAuth en Exchange, vea [configurar la autenticación OAuth con SharePoint 2013 y Skype empresarial Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.
