---
title: Configurar aplicaciones de partners en Skype Empresarial Server 2015 y Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumen: configure la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.'
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110116"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicaciones de partners en Skype Empresarial Server y Exchange Server
 
**Resumen:** Configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.
  
La autenticación de servidor a servidor normalmente requiere dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de terceros. Si el servidor A y el servidor B necesitan comunicarse, estos dos servidores suelen empezar por ponerse en contacto con un servidor de tokens y obtener un token de seguridad de confianza mutua. A continuación, el servidor A presenta ese token de seguridad al servidor B (y viceversa) como una forma de garantizar su autenticidad y fiabilidad.
  
Ahora bien, eso no es sino una regla general. Skype Empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros al comunicarse entre sí; esto se debe a que estos productos de servidor pueden crear tokens de seguridad que pueden ser aceptados entre sí sin necesidad de un servidor de tokens independiente. (Esta funcionalidad solo está disponible en Skype Empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).
  
Para configurar la autenticación de servidor a servidor entre Skype Empresarial Server y Exchange Server debe hacer dos cosas: 1) debe asignar los certificados adecuados a cada servidor; y, 2) debe configurar cada servidor para que sea una aplicación asociada del otro servidor: esto significa que debe configurar Skype Empresarial Server para que sea una aplicación de socio para Exchange Server y debe configurar Exchange Server para que sea una aplicación de socio para Skype Empresarial Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurar Skype Empresarial Server para que sea una aplicación de partner para Exchange Server

La forma más sencilla de configurar Skype Empresarial Server para que sea una aplicación asociada con Exchange Server 2016 o Exchange Server 2013 es ejecutar el script Configure-EnterprisePartnerApplication.ps1, un script de Windows PowerShell que se incluye con Exchange Server. Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos de autenticación de Skype Empresarial Server; este suele ser el nombre de dominio completo del grupo de Skype Empresarial Server seguido del sufijo /metadata/json/1. Por ejemplo:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar Skype Empresarial Server como una aplicación asociada, abra el Shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se ha instalado en la unidad C: y que usa la ruta de acceso de carpeta predeterminada):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Después de configurar la aplicación de socio, se recomienda detener y reiniciar Internet Information Services (IIS) en el buzón de Exchange y los servidores de acceso de cliente. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde el Shell de administración de Exchange o desde cualquier otra ventana de comandos que se ejecute con privilegios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurar Exchange Server para ser una aplicación de socio para Skype Empresarial Server

Después de configurar Skype Empresarial Server para que sea una aplicación asociada para Exchange Server 2016 o Exchange Server 2013, debe configurar Exchange Server para que sea una aplicación asociada para Skype Empresarial Server. Para ello, use el Shell de administración de Skype Empresarial Server y especifique el documento de metadatos de autenticación para Exchange; normalmente será el URI del servicio de detección automática de Exchange seguido del sufijo /metadata/json/1. Por ejemplo:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

En Skype Empresarial Server, las aplicaciones asociadas se configuran mediante el cmdlet [New-CsPartnerApplication.](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Además de especificar el URI de metadatos, también debe establecer el nivel de confianza de la aplicación en Full; esto permitirá a Exchange representarse a sí mismo y a cualquier usuario autorizado en el dominio. Por ejemplo:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, puede crear una aplicación asociada copiando y modificando el código de script que se encuentra en la documentación de autenticación de servidor a servidor de Skype Empresarial Server. Vea el [artículo Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) para obtener más información.
  
Si ha configurado correctamente aplicaciones de asociado para Skype Empresarial Server y Exchange Server, también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos. Skype Empresarial Server incluye un cmdlet Windows PowerShell, [Test-CsExStorageConnectivity,](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio de almacenamiento de Skype Empresarial Server puede conectarse a Exchange Server. Para ello, el cmdlet se conecta al buzón de un usuario de Exchange Server, escribe un elemento en la carpeta Historial de conversaciones para ese usuario y, a continuación, (opcionalmente) elimina ese elemento.
  
Para probar la integración de Skype Empresarial Server y Exchange Server, ejecute un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

En el comando anterior, SipUri representa la dirección SIP de un usuario con una cuenta en Exchange Server; el comando producirá un error en esta no es una cuenta de usuario válida.
  
> [!NOTE]
> Si recibe una respuesta 401 de este cmdlet, probablemente se debe a que la configuración predeterminada de Exchange no incluye compatibilidad para aceptar tokens de Oauth. Para obtener más información acerca del uso de Oauth en Exchange, vea [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help). 
  
Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.