---
title: Configurar la implementación local para la difusión de reunión de Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumen: Obtenga información sobre los pasos que necesarios para llevar a cabo para configurar Difundir presentación de reunión de Skype para su Skype local para la implementación híbrida de Business Server.'
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069472"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Resumen:** Obtenga información sobre los pasos que necesarios para llevar a cabo para configurar Difundir presentación de reunión de Skype para su Skype local para la implementación híbrida de Business Server.
  
Difundir presentación de reunión de Skype es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype para Business Server local y desea usar Difundir presentación de reunión de Skype en su entorno, debe seguir los pasos de configuración en este tema. Antes de empezar, el entorno debe configurarse para la implementación híbrida con Skype para profesionales en línea. Para más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar su entorno híbrido para difundir presentación de reunión de Skype

Debe hacer lo siguiente para preparar su entorno para difundir presentación de reunión de Skype:
  
- Configurar la federación con Skype para recursos en línea de negocio
    
- Configurar los dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la federación con Skype para recursos en línea de negocio

Para habilitar la federación con Skype para recursos en línea de negocio, debe configurar el acceso externo para un proveedor SIP federado. Para llevar a cabo mediante el uso de la Skype para el Panel de Control de Business Server, siga estos pasos:
  
1. Inicie el Skype para el Panel de Control de servidor empresarial y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con la siguiente configuración:
    
|||
|:-----|:-----|
|**Habilitar las comunicaciones con este proveedor:** <br/> |Seleccionado  <br/> |
|**Nombre del proveedor:** <br/> |LyncOnlineResources  <br/> |
|**Servicio perimetral de acceso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nivel de verificación predeterminado:** <br/> |Permita a los usuarios comunicarse con todos los usuarios con este proveedor.  <br/> |
   
También puede habilitar la federación con Skype para recursos en línea de negocio ejecutando el siguiente cmdlet en el Skype para Shell de administración de servidor empresarial:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar los dominios federados SIP

A continuación, deberá agregar dominios federados SIP a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP. Incluyen estos dominios son para los datos regionales centros usados en Skype para profesionales en línea.
  
1. Inicie el Skype para el Panel de Control de servidor empresarial y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.
    
3. Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
También puede configurar el acceso externo para los dominios federados SIP mediante la ejecución de los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez que haya completado estos pasos de configuración puede empezar a usar Difundir presentación de reunión de Skype en su implementación. Para obtener más información acerca de la difusión de reunión de Skype, vea [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [Guía de administración de Difundir presentación de Skype reunión](https://go.microsoft.com/fwlink/?LinkId=617075).
  

