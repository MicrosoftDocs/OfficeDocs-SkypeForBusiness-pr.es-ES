---
title: Habilitar y deshabilitar el desvío de medios
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar el desvío de medios mediante el uso de la Skype para el Panel de Control de servidor empresarial.
ms.openlocfilehash: f595ab5380575f34c0a470cb58c82459841ee4d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222761"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitación y deshabilitación de medios de omisión de Skype Business Server

Use los procedimientos de este artículo para habilitar o deshabilitar el desvío de medios mediante el uso de la Skype para el Panel de Control de servidor empresarial.

## <a name="enable-network-media-bypass"></a>Habilitar desvío de medios de red 

Configuración de desvío de medios se aplica globalmente a través de un Skype para la implementación de Business Server. Desvío de medios permite que las llamadas a omitir el servidor de mediación. Para obtener más información acerca de cuándo se deben usar desvío de medios, vea [Plan para los medios de desvío](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Puede habilitar y configurar el desvío de medios desde el Skype para el Panel de Control de servidor empresarial.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar y configurar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.

4.  En la página **Global** , haga clic en la configuración **Global** . Siempre hay sólo una configuración, y siempre se denomina Global.

5.  En el menú **Edición** , haga clic en **Ver detalles**.

6.  En la página **Editar configuración Global** , haga clic en la casilla de verificación **Habilitar el desvío de medios** .

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre**   Seleccione esta opción para intentar medios desvío en todas las llamadas. Esta opción no estará disponible si está habilitado el control de admisión de llamadas (CAC). Si no está habilitado el CAC, seleccione esta opción en las siguientes situaciones:
        
          - No es necesario para el control del ancho de banda.
        
          - No es necesario para una configuración específica para determinar cuándo debe producirse el desvío.
        
          - Existe plena conectividad entre las puertas de enlace y los clientes.
    
      - **Usar los sitios y configuración de la región**   CAC si está habilitado, esta opción está seleccionada de manera predeterminada y no se puede cambiar. Cuando se selecciona esta opción, se usará para determinar cuándo es posible desvío de medios regiones y sitios de la configuración de red. Si selecciona esta opción, puede elegir habilitar el desvío para sitios que no están asignados. Haga clic en la casilla de verificación **Habilitar el desvío para sitios sin asignar** sólo si tiene uno o más grandes sitios asociados con la misma región que no tienen restricciones de ancho de banda (por ejemplo, un sitio central grande) y también tiene algunos sitios de sucursal asociadas con la misma región que tienen restricciones de ancho de banda. Cuando se habilita el desvío para sitios sin asignar, configuración se simplifica porque especificar sólo las subredes asociadas con los sitios de sucursal, en lugar de tener que especificar todas las subredes asociadas con todos los sitios. Se recomienda que no active la casilla de verificación **Habilitar el desvío para sitios sin asignar** si está habilitado el CAC.

8.  Haga clic en **Confirmar** para guardar los cambios.


## <a name="disable-network-media-bypass"></a>Deshabilitar el desvío de medios de red

Configuración de desvío de medios se aplica globalmente a través de un Skype para la implementación de Business Server. Desvío de medios permite que las llamadas a omitir el servidor de mediación. Para obtener más información acerca de cuándo se deben usar desvío de medios, vea [Plan para los medios de desvío](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Puede deshabilitar el desvío de medios desde el Skype para el Panel de Control de servidor empresarial. 


### <a name="to-disable-media-bypass"></a>Para deshabilitar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.

4.  En la página **Global** , haga clic en la configuración **Global** . Siempre hay sólo una configuración, y siempre se denomina Global.

5.  En el menú **Edición** , haga clic en **Ver detalles**.

6.  En la página **Editar configuración Global** , desactive la casilla de verificación **Habilitar el desvío de medios** .

7.  Haga clic en **Confirmar** para guardar los cambios.

  