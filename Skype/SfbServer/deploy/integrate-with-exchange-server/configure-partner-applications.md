---
title: Configurar aplicaciones de asociado en Skype Empresarial Server 2015 y Exchange Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumen: configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.'
ms.openlocfilehash: bb76b34bdf1a5a8a6c1b60fc200c46112985f31c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864247"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicaciones de partners en Skype Empresarial Server y Exchange Server
 
**Resumen:** Configurar la autenticación de servidor a servidor para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.
  
La autenticación de servidor a servidor normalmente requiere dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de terceros. Si el servidor A y el servidor B necesitan comunicarse, estos dos servidores suelen empezar por ponerse en contacto con un servidor de tokens y obtener un token de seguridad de confianza mutua. A continuación, el servidor A presenta ese token de seguridad al servidor B (y viceversa) como una forma de garantizar su autenticidad y fiabilidad.
  
Ahora bien, eso no es sino una regla general. Skype Empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros al comunicarse entre sí; esto se debe a que estos productos de servidor pueden crear tokens de seguridad que pueden ser aceptados entre sí sin necesidad de un servidor de tokens independiente. (Esta funcionalidad solo está disponible en Skype Empresarial Server, Exchange Server 2016, Exchange Server 2013 y SharePoint Server 2013. Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).
  
Para configurar la autenticación de servidor a servidor entre Skype Empresarial Server y Exchange Server debe hacer dos cosas: 1) debe asignar los certificados adecuados a cada servidor; y, 2) debe configurar cada servidor para que sea una aplicación de socio del otro servidor: esto significa que debe configurar Skype Empresarial Server para que sea una aplicación de socio para Exchange Server y debe configurar Exchange Server para que sea una aplicación de socio para Skype Empresarial Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurar Skype Empresarial Server para que sea una aplicación de partner para Exchange Server

La forma más sencilla de configurar Skype Empresarial Server para que sea una aplicación asociada con Exchange Server 2016 o Exchange Server 2013 es ejecutar el script Configure-EnterprisePartnerApplication.ps1, un script de Windows PowerShell que se incluye con Exchange Server. Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos Skype Empresarial Server autenticación; normalmente será el nombre de dominio completo del grupo de servidores Skype Empresarial Server seguido del sufijo /metadata/json/1. Por ejemplo:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar Skype Empresarial Server como una aplicación asociada, abra el Shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en la unidad C: y que use la ruta de acceso de carpeta predeterminada):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Después de configurar la aplicación de socio, se recomienda detener y reiniciar Internet Information Services (IIS) en el buzón de correo Exchange servidores de acceso de cliente. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde el Shell Exchange de administración o desde cualquier otra ventana de comandos que se ejecute con privilegios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuración de Exchange Server para ser una aplicación de partners para Skype Empresarial Server

Después de configurar Skype Empresarial Server para que sea una aplicación de socio para Exchange Server 2016 o Exchange Server 2013, debe configurar Exchange Server para que sea una aplicación asociada para Skype Empresarial Server. Para ello, use el Shell Skype Empresarial Server administración y especifique el documento de metadatos de autenticación para Exchange; este suele ser el URI del servicio de detección automática Exchange seguido del sufijo /metadata/json/1. Por ejemplo:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

En Skype Empresarial Server, las aplicaciones asociadas se configuran mediante el cmdlet [New-CsPartnerApplication.](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Además de especificar el URI de metadatos, también debe establecer el nivel de confianza de la aplicación en Full; esto permitirá que Exchange represente a sí mismo y a cualquier usuario autorizado en el dominio. Por ejemplo:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, puede crear una aplicación asociada copiando y modificando el código de script que se encuentra en la Skype Empresarial Server de autenticación de servidor a servidor. Vea el artículo Administrar la autenticación de servidor a servidor [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) y las aplicaciones asociadas en Skype Empresarial Server para obtener más información.
  
Si ha configurado correctamente aplicaciones de asociado para Skype Empresarial Server y Exchange Server, también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos. Skype Empresarial Server incluye un cmdlet Windows PowerShell, [Test-CsExStorageConnectivity,](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio Skype Empresarial Server Storage se puede conectar a Exchange Server. Para ello, el cmdlet se conecta al buzón de un usuario de Exchange Server, escribe un elemento en la carpeta Historial de conversaciones para ese usuario y, a continuación, (opcionalmente) elimina ese elemento.
  
Para probar la integración de Skype Empresarial Server y Exchange Server, ejecute un comando similar al siguiente desde el Shell Skype Empresarial Server administración:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

En el comando anterior, sipuri representa la dirección SIP de un usuario con una cuenta en Exchange Server; el comando producirá un error en esta no es una cuenta de usuario válida.
  
> [!NOTE]
> Si recibe una respuesta 401 de este cmdlet, probablemente se debe a que la configuración predeterminada de Exchange no incluye compatibilidad para aceptar tokens de Oauth. Para obtener más información acerca del uso de Oauth en Exchange, vea [Configure OAuth authentication with SharePoint 2013 and Skype Empresarial Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help). 
  
Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.