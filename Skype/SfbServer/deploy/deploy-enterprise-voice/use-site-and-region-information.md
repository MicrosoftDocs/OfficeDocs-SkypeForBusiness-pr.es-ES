---
title: Configurar la configuración global de omisión de medios en Skype empresarial Server para usar la información del sitio y de la región
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurar la omisión de elementos multimedia para usarlos solo en determinados sitios y regiones de la telefonía IP empresarial de Skype empresarial Server.
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766943"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar la configuración global de omisión de medios en Skype empresarial Server para usar la información del sitio y de la región
 
Configurar la omisión de elementos multimedia para usarlos solo en determinados sitios y regiones de la telefonía IP empresarial de Skype empresarial Server. 
  
 Si usa los pasos de este tema para establecer la configuración global de omisión de medios, se supone que no tiene una buena conectividad entre todos los puntos de conexión de Skype empresarial y cualquier elemento del mismo nivel para el cual haya configurado el bypass de medios en la conexión troncal.
  
> [!NOTE]
> La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para la omisión de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del omisión de medios. 
  
Para que la omisión de elementos multimedia funcione correctamente, debe ser coherente entre un sitio definido en el generador de topologías y se define al configurar las regiones de red y los sitios de red. Por ejemplo, si tiene un sitio de sucursal que ha definido en el generador de topología y tiene una puerta de enlace RTC implementada, ese sitio de sucursal debe estar configurado con una directiva de telefonía IP empresarial que permita a los usuarios de la sucursal enrutar las llamadas RTC a través de la RTC. puerta de enlace en el sitio de la sucursal.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
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
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación de la omisión de medios. Para obtener más información, consulte [implementar regiones, sitios y subredes de la red en Skype empresarial](deploy-network.md). 
  
## <a name="see-also"></a>Vea también

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

