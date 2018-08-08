---
title: Configurar la configuración global de desvío de medios en Skype para Business Server usar la información de sitio y región
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurar el desvío de medios que se usará para sólo ciertos sitios y regiones en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 081be80d969c2503abc7e2de4e9865b6057a363b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995982"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar la configuración global de desvío de medios en Skype para Business Server usar la información de sitio y región
 
Configurar el desvío de medios que se usará para sólo ciertos sitios y regiones en Skype para Business Server Enterprise Voice. 
  
 Si usa el desvío de los pasos descritos en este tema para establecer la configuración global para los medios, la suposición es que no tienen una buena conectividad entre todos los Skype para los extremos de negocio y cualquier elemento del mismo nivel para los que ha configurado el desvío de medios en la conexión del tronco.
  
> [!NOTE]
> La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para la omisión de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del omisión de medios. 
  
El desvío de medios para que funcione correctamente debe haber coherencia entre un sitio como se define en el generador de topología y tal y como se define al configurar regiones de red y sitios de red. Por ejemplo, si tiene un sitio de sucursal que definido en el generador con sólo una puerta de enlace RTC implementada, a continuación, ese sitio de sucursal debe estar configurado con una directiva de Enterprise Voice que permite a los usuarios del sitio de sucursal tiene sus llamadas RTC se enrutan a través de la RTC puerta de enlace en el sitio de sucursal.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
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
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación de la omisión de medios. Para obtener información detallada, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](deploy-network.md). 
  
## <a name="see-also"></a>Vea también

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

