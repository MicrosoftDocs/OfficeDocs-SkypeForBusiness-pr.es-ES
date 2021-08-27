---
title: Configurar la omisión de medios de configuración global Skype Empresarial Server para usar información de sitio y región
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configure la omisión de medios para que se utilice solo para determinados sitios y regiones de Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d90393c19dffaac425025379258a0ceae24da9cf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588992"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar la omisión de medios de configuración global Skype Empresarial Server para usar información de sitio y región
 
Configure la omisión de medios para que se utilice solo para determinados sitios y regiones de Skype Empresarial Server Telefonía IP empresarial. 
  
 Si usa los pasos de este tema para configurar la configuración global para la omisión de medios, se supone que no tiene una buena conectividad entre todos los puntos de conexión de Skype Empresarial y cualquier punto del mismo nivel para el que configuró la omisión de medios en la conexión troncal.
  
> [!NOTE]
> La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para el desvío de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del desvío de medios. 
  
Para que la omisión de medios funcione correctamente, debe haber coherencia entre un sitio tal como se define en el Generador de topologías y tal como se define al configurar regiones de red y sitios de red. Por ejemplo, si tiene un sitio de sucursal que definió en el Generador de topologías como que solo tiene implementada una puerta de enlace RTC, ese sitio de sucursal debe configurarse con una directiva Telefonía IP empresarial que permita a los usuarios de sitios de sucursal enrutar sus llamadas RTC a través de la puerta de enlace RTC en el sitio de sucursal.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.  
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la tabla.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.
    
5. Haga clic en **Usar la configuración de sitios y regiones**.
    
6. Si es necesario, seleccione la casilla **Habilitar desvío para sitios sin asignar**.
    
    > [!NOTE]
    > Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas. 
  
7. Haga clic en **Confirmar**.
    
A continuación, agregue subredes al sitio de red, como se describe en [Asociar una subred a un sitio de red.](deploy-network.md#BKMK_AssociateSubnets) Cuando haya asociado todas las subredes a sitios de red, la implementación del desvío de medios habrá finalizado.
> [!IMPORTANT]
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación del desvío de medios. Para obtener más información, vea [Deploy network regions, sites and subnets in Skype Empresarial](deploy-network.md). 
  
## <a name="see-also"></a>Consulte también

[Asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets)

