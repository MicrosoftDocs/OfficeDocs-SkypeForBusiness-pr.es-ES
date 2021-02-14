---
title: Configurar la implementación local para difusión de reunión de Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumen: obtenga información sobre los pasos que debe realizar para configurar la Difusión de reunión de Skype para su implementación híbrida de Skype Empresarial Server local.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820710"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar la implementación local para difusión de reunión de Skype
 
**Resumen:** Obtenga información sobre los pasos que debe realizar para configurar la Difusión de reunión de Skype para su implementación híbrida de Skype Empresarial Server local.
  
Difusión de reunión de Skype es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype Empresarial Server local y desea usar difusión de reunión de Skype en su entorno, tendrá que seguir los pasos de configuración de este tema. Antes de empezar, el entorno debe configurarse para la implementación híbrida con Skype Empresarial Online. Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar el entorno híbrido para difusión de reunión de Skype

Deberá hacer lo siguiente para preparar su entorno para difusión de reunión de Skype:
  
- Configurar la federación con recursos de Skype Empresarial Online
    
- Configurar dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la federación con recursos de Skype Empresarial Online

Para habilitar la federación con recursos de Skype Empresarial Online, debe configurar el acceso externo para un proveedor federado SIP. Para ello, use el Panel de control de Skype Empresarial Server, siga estos pasos:
  
1. Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP y** haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con las siguientes opciones:
    
|||
|:-----|:-----|
|**Habilite las comunicaciones con este proveedor:** <br/> |Seleccionado  <br/> |
|**Nombre del proveedor:** <br/> |LyncOnlineResources  <br/> |
|**Servicio perimetral de acceso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nivel de verificación predeterminado:** <br/> |Permitir que los usuarios se comuniquen con todos los usuarios que usan este proveedor.  <br/> |
   
También puede habilitar la federación con recursos de Skype Empresarial Online ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar dominios federados SIP

A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados y cree 4 nuevos dominios federados SIP. Estos dominios son para los centros de datos regionales usados en Skype Empresarial Online.
  
1. Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP y** haga clic en **Nuevo**.
    
3. Para el **nombre de dominio (o FQDN):**, escriba el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
También puede configurar el acceso externo para los dominios federados SIP ejecutando los cmdlets siguientes en el Shell de administración de Skype Empresarial Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez que haya completado estos pasos de configuración, puede empezar a usar Difusión de reunión de Skype en su implementación. Para obtener más información acerca de difusión de reunión de Skype, consulte ¿Qué es [una Difusión](https://go.microsoft.com/fwlink/?LinkId=617071) de reunión de Skype? y guía de administración de [difusión de reunión de Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)
  

