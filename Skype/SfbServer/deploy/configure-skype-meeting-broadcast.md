---
title: Configurar la implementación local para la difusión de reunión de Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumen: Obtenga información sobre los pasos que debe realizar para configurar la difusión de reunión de Skype para su implementación híbrida local de Skype empresarial Server.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002810"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Resumen:** Obtenga más información sobre los pasos que debe realizar para configurar la difusión de reunión de Skype para su implementación híbrida de Skype empresarial Server local.
  
Difusión de reunión de Skype es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype empresarial Server local y desea usar difusión de reunión de Skype en su entorno, tendrá que seguir los pasos de configuración de este tema. Antes de empezar, debe configurar su entorno para que sea híbrido con Skype empresarial online. Para más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar el entorno híbrido para difusión de reunión de Skype

Tendrá que seguir estos pasos para preparar el entorno para la difusión de reunión de Skype:
  
- Configurar la Federación con recursos de Skype empresarial online
    
- Configurar los dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la Federación con recursos de Skype empresarial online

Para habilitar la Federación con recursos de Skype empresarial online, debe configurar el acceso externo para un proveedor federado de SIP. Para hacerlo con el panel de control de Skype empresarial Server, siga estos pasos:
  
1. Inicie el panel de control de Skype empresarial Server y seleccione **acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con la siguiente configuración:
    
|||
|:-----|:-----|
|**Habilitar las comunicaciones con este proveedor:** <br/> |Seleccionado  <br/> |
|**Nombre del proveedor:** <br/> |LyncOnlineResources  <br/> |
|**Servicio perimetral de acceso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nivel de verificación predeterminado:** <br/> |Permita a los usuarios comunicarse con todos los usuarios con este proveedor.  <br/> |
   
También puede habilitar la Federación con recursos de Skype empresarial online ejecutando el siguiente cmdlet en el shell de administración de Skype empresarial Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar los dominios federados SIP

A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP. Estos dominios incluyen los centros de datos regionales que se usan en Skype empresarial online.
  
1. Inicie el panel de control de Skype empresarial Server y seleccione **acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.
    
3. Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
También puede configurar el acceso externo para los dominios federados de SIP ejecutando los siguientes cmdlets en el shell de administración de Skype empresarial Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez que haya completado estos pasos de configuración, puede empezar a usar difusión de reunión de Skype en su implementación. Para obtener más información sobre la difusión de reunión de Skype, vea [¿Qué es una difusión de reunión de Skype? y la](https://go.microsoft.com/fwlink/?LinkId=617071) [Guía de administrador de difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617075).
  

