---
title: Habilitar y deshabilitar la omisión de medios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios con el panel de control de Skype empresarial Server.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817549"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar y deshabilitar la omisión de medios en Skype Empresarial Server

Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios con el panel de control de Skype empresarial Server.

## <a name="enable-network-media-bypass"></a>Habilitar omisión de medios de red 

La configuración de omisión de medios se aplica globalmente en una implementación de Skype empresarial Server. La omisión de medios permite que las llamadas omitan el servidor de mediación. Para obtener información sobre Cuándo usar la omisión de elementos multimedia, consulte [planear la omisión de medios](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Puede habilitar y configurar la omisión de medios desde el panel de control de Skype empresarial Server.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar y configurar la omisión de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.

4.  En la página **global** , haga clic en la configuración **global** . Siempre hay una sola configuración y siempre se denomina global.

5.  En el menú **Editar** , haga clic en **Ver detalles**.

6.  En la página **Editar configuración global** , haga clic en la casilla de verificación **Habilitar omisión de medios** .

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre seleccione**   esta opción para intentar la omisión de medios en todas las llamadas. Esta opción no estará disponible si el control de admisión de llamada (CAC) está habilitado. Si CAC no está habilitado, seleccione esta opción en las siguientes situaciones:
        
          - No es necesario el control del ancho de banda.
        
          - No es necesario que la configuración específica determine Cuándo debe pasar el bypass.
        
          - Hay conectividad completa entre las puertas de enlace y los clientes.
    
      - **Usar la configuración**   de sitios y regiones si CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar. Cuando esta opción está seleccionada, se usarán regiones y sitios de configuración de red para determinar cuándo es posible la omisión de medios. Si selecciona esta opción, puede habilitar el omisión de sitios que no están asignados. Haga clic en la casilla **de verificación Habilitar el omisión de sitios no asignados** solo si tiene uno o varios sitios grandes asociados a la misma región que no tienen restricciones de ancho de banda (por ejemplo, un sitio central grande) y también tiene algunos sitios de rama asociados a la misma región que tienen restricciones de ancho de banda. Cuando habilita el bypass para sitios no asignados, la configuración se simplifica porque especifica solo las subredes asociadas a las sucursales en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Le recomendamos que no active la casilla **Habilitar omisión para sitios no asignados** si CAC está habilitado.

8.  Haga clic en **confirmar** para guardar los cambios.


## <a name="disable-network-media-bypass"></a>Deshabilitar omisión de medios de red

La configuración de omisión de medios se aplica globalmente en una implementación de Skype empresarial Server. La omisión de medios permite que las llamadas omitan el servidor de mediación. Para obtener información sobre Cuándo usar la omisión de elementos multimedia, consulte [planear la omisión de medios](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Puede deshabilitar la omisión de medios desde el panel de control de Skype empresarial Server. 


### <a name="to-disable-media-bypass"></a>Para deshabilitar la omisión de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.

4.  En la página **global** , haga clic en la configuración **global** . Siempre hay una sola configuración y siempre se denomina global.

5.  En el menú **Editar** , haga clic en **Ver detalles**.

6.  En la página **Editar configuración global** , desactive la casilla **Habilitar omisión de medios** .

7.  Haga clic en **confirmar** para guardar los cambios.

  
