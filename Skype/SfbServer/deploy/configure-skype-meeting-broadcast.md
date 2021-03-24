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
description: 'Summary: Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.'
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103696"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar la implementación local para difusión de reunión de Skype
 
**Resumen:** Obtenga información sobre los pasos que debe realizar para configurar la difusión de reuniones de Skype para la implementación híbrida de Skype Empresarial Server local.
  
Difusión de reunión de Skype es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype Empresarial Server local y desea usar difusión de reunión de Skype en su entorno, deberá seguir los pasos de configuración de este tema. Antes de empezar, el entorno debe configurarse para híbrido con Skype Empresarial Online. Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar el entorno híbrido para difusión de reunión de Skype

Deberás hacer lo siguiente para preparar el entorno para la difusión de reuniones de Skype:
  
- Configurar la federación con recursos de Skype Empresarial Online
    
- Configurar dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la federación con recursos de Skype Empresarial Online

Para habilitar la federación con recursos de Skype Empresarial Online, debe configurar el acceso externo para un proveedor federado SIP. Para ello, use el Panel de control de Skype Empresarial Server siga estos pasos:
  
1. Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP y** haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con las siguientes opciones:
    
|||
|:-----|:-----|
|**Habilitar las comunicaciones con este proveedor:** <br/> |Seleccionado  <br/> |
|**Nombre del proveedor:** <br/> |LyncOnlineResources  <br/> |
|**Servicio perimetral de acceso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nivel de verificación predeterminado:** <br/> |Permitir que los usuarios se comuniquen con todos los usuarios que usan este proveedor.  <br/> |
   
También puede habilitar la federación con recursos de Skype Empresarial Online ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar dominios federados SIP

A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados, creando 4 nuevos dominios federados SIP. Estos dominios incluyen los centros de datos regionales usados en Skype Empresarial Online.
  
1. Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.
    
3. Para el **nombre de dominio (o FQDN):**, escriba el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
También puede configurar el acceso externo para dominios federados SIP ejecutando los cmdlets siguientes en el Shell de administración de Skype Empresarial Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez completados estos pasos de configuración, puede empezar a usar difusión de reunión de Skype en la implementación. Para obtener más información acerca de la difusión de reuniones de Skype, vea [¿Qué](https://go.microsoft.com/fwlink/?LinkId=617071) es una difusión de reunión de Skype? y Guía de administración de [difusión de reunión de Skype](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).
