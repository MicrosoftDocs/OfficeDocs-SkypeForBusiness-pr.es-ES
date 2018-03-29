---
title: Configurar la implementación local para la difusión de reunión de Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
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
description: 'Resumen: Conozca los pasos que debe realizar para configurar difusión de reunión de Skype para tu Skype local para la implementación de Business Server híbrido.'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar la implementación local para la difusión de reunión de Skype
 
**Resumen:** Obtenga información acerca de los pasos que debe realizar para configurar difusión de reunión de Skype para tu Skype local para la implementación de Business Server híbrido.
  
Difundir reunión de Skype es un servicio en línea que forma parte de Office 365. Si está ejecutando Skype para Business Server local y desea utilizar Skype reunión difusión en su entorno, debe seguir los pasos de este tema. Antes de comenzar, su entorno debe configurarse para híbrido con Skype para los negocios en línea. Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y [conectividad de implementación híbrida entre Skype para Business Server y Skype para los negocios en línea](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar el entorno de híbrido para difundir reunión de Skype

Debe hacer lo siguiente para preparar el entorno para difundir reunión de Skype:
  
- Configurar la federación con Skype para recursos en línea de negocio
    
- Configurar los dominios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar la federación con Skype para recursos en línea de negocio

Para habilitar la federación con Skype para recursos en línea de negocio, debe configurar el acceso externo de un proveedor de SIP federados. Para ello utilizando el Skype para Panel de Control de Business Server, siga estos pasos:
  
1. Inicie el Skype para Business Server Control Panel y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.
    
3. Configure el nuevo proveedor con la siguiente configuración:
    
|||
|:-----|:-----|
|**Habilitar las comunicaciones con este proveedor:** <br/> |Seleccionado  <br/> |
|**Nombre del proveedor:** <br/> |LyncOnlineResources  <br/> |
|**Servicio perimetral de acceso (FQDN):** <br/> |sipfed.Resources.Lync.com  <br/> |
|**Nivel de verificación predeterminado:** <br/> |Permita a los usuarios comunicarse con todos los usuarios con este proveedor.  <br/> |
   
También puede habilitar la federación con Skype recursos empresariales en línea ejecutando el siguiente cmdlet en el Skype para el Shell de administración de servidor empresarial:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar los dominios federados SIP

A continuación, debe agregar dominios SIP federados a la lista de dominios permitidos. Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP. Incluyen estos dominios son para los datos regionales centros utilizados en Skype para los negocios en línea.
  
1. Inicie el Skype para Business Server Control Panel y seleccione **Acceso externo** a la izquierda.
    
2. Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.
    
3. Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
También puede configurar el acceso externo para dominios SIP federado ejecutando los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

Una vez haya completado estos pasos de configuración puede empezar a usar Skype reunión difusión en su implementación. Para obtener más información acerca de la difusión de la reunión de Skype, consulte [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [Guía de administración de difundir reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617075).
  

