---
title: Configurar la implementación local para la difusión Skype reunión
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Summary: Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype Empresarial Server hybrid deployment.'
ms.openlocfilehash: 99ba1733dc8c353dc17f9a4c9a51a9ed00410d27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013714"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar la implementación local para la difusión Skype reunión
 
**Resumen:** Obtenga información sobre los pasos que debe realizar para configurar la difusión Skype reunión para su implementación híbrida Skype Empresarial Server local.
  
Skype Difusión de reuniones es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype Empresarial Server local y desea usar Skype difusión de reunión en su entorno, deberá seguir los pasos de configuración de este tema. Antes de empezar, el entorno debe configurarse para híbrido con Skype Empresarial Online. Para obtener más información, vea [Plan hybrid connectivity between Skype Empresarial Server and Skype Empresarial Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype Empresarial Server and Skype Empresarial [Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar el entorno híbrido para la difusión Skype reunión

Deberá hacer lo siguiente para preparar el entorno para la difusión Skype reunión:
  
- Configurar la federación con Skype Empresarial en línea
    
- Configurar dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la federación con Skype Empresarial en línea

Para habilitar la federación con Skype Empresarial en línea, debe configurar el acceso externo para un proveedor federado SIP. Para ello, use el Panel de control Skype Empresarial Server siga estos pasos:
  
1. Inicie el panel Skype Empresarial Server control y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP y** haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con las siguientes opciones:
    
   - **Habilitar las comunicaciones con este proveedor:** Seleccionado
   - **Nombre del proveedor:** LyncOnlineResources
   - **Servicio perimetral de acceso (FQDN): sipfed.resources.lync.com**
   - **Nivel de comprobación predeterminado:** Permitir que los usuarios se comuniquen con todos los usuarios que usan este proveedor. 
   
También puede habilitar la federación con Skype Empresarial en línea mediante la ejecución del siguiente cmdlet en el Shell Skype Empresarial Server administración:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar dominios federados SIP

A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados, creando 4 nuevos dominios federados SIP. Estos dominios incluyen los centros de datos regionales usados en Skype Empresarial Online.
  
1. Inicie el panel Skype Empresarial Server control y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.
    
3. Para el **nombre de dominio (o FQDN):**, escriba el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
También puede configurar el acceso externo para los dominios federados SIP ejecutando los siguientes cmdlets en el Shell de administración Skype Empresarial Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez que haya completado estos pasos de configuración, puede empezar a usar Skype difusión de reuniones en la implementación. Para obtener más información acerca Skype difusión de reuniones, vea ¿Qué es una difusión Skype [reunión?](https://go.microsoft.com/fwlink/?LinkId=617071) y Skype de administración de difusión [de reuniones](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).
