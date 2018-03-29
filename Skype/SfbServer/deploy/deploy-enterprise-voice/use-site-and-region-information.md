---
title: Configuración multimedia bypass global en Skype para Business Server 2015 utilizar la información del sitio y región
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurar la omisión de medios destinados a sólo algunos sitios y áreas de Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: cebfa9d416fe3e68cd5615ae11616707ba1f60a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a>Configuración multimedia bypass global en Skype para Business Server 2015 utilizar la información del sitio y región
 
Configurar la omisión de medios destinados a sólo algunos sitios y áreas de Skype para Telefonía IP empresarial de Business Server. 
  
 Si utiliza omitir los pasos de este tema para configurar opciones globales de los medios de comunicación, la suposición es que no tiene buena conectividad entre todos los Skype para extremos de negocio y cualquier elemento del mismo nivel para el que configuró omisión de medios en la conexión de troncal.
  
> [!NOTE]
> La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para la omisión de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del omisión de medios. 
  
Para omitir los medios para trabajar correctamente debe haber coherencia entre un sitio tal como se define en el generador de topología y tal y como se define al configurar regiones de red y sitios de red. Por ejemplo, si tiene un sitio de sucursal que definió en el generador de topología tiene sólo una puerta de enlace PSTN implementado, entonces ese sitio de la sucursal debe estar configurado con una directiva de Telefonía IP empresarial que permite a los usuarios del sitio de sucursal sus llamadas PSTN que se enrutan a través de la red PSTN puerta de enlace en el sitio de la sucursal.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la tabla.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.
    
5. Haga clic en **Usar la configuración de sitios y regiones**.
    
6. Si es necesario, seleccione la casilla **Habilitar omisión para sitios sin asignar**.
    
    > [!NOTE]
    > Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tengan restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita la omisión para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas. 
  
7. Haga clic en **Confirmar**.
    
A continuación, agregue subredes al sitio de red, como se describe en [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Cuando haya asociado todas las subredes a sitios de red, la implementación de la omisión de medios habrá finalizado.
> [!IMPORTANT]
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación de la omisión de medios. Para obtener más información, vea [implementar regiones de red, sitios y subredes en Skype para negocios 2015](deploy-network.md). 
  
## <a name="see-also"></a>Vea también

#### 

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

