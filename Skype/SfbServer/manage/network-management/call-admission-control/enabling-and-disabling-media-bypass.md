---
title: Habilitar y deshabilitar la omisión de medios
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios mediante el Panel de control de Skype Empresarial Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816500"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar y deshabilitar la omisión de medios en Skype Empresarial Server

Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios mediante el Panel de control de Skype Empresarial Server.

## <a name="enable-network-media-bypass"></a>Habilitar la omisión de medios de red 

La configuración de omisión de medios se aplica globalmente en una implementación de Skype Empresarial Server. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener más información acerca de cuándo usar la omisión de medios, vea [Planear la omisión de medios.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Puede habilitar y configurar la omisión de medios desde el Panel de control de Skype Empresarial Server.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar y configurar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página **Editar configuración global**, haga clic en la casilla **Habilitar desvío de medios**.

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre**   Seleccione esta opción para intentar la omisión de medios en todas las llamadas. Esta opción no estará disponible si se ha habilitado el control de admisión de llamadas (CAC). Si el CAC no está habilitado, seleccione esta opción en las situaciones siguientes:
        
          - No es necesario controlar el ancho de banda.
        
          - No se necesita una configuración específica para saber cuándo debe producirse el desvío.
        
          - Existe plena conectividad entre las puertas de enlace y los clientes.
    
      - **Usar la configuración de sitios y regiones**   Si el CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar. Cuando se selecciona esta opción, los sitios y regiones de configuración de red se usarán para determinar cuando resulta posible el desvío de medios. Si selecciona esta opción, puede optar por habilitar el desvío para sitios que no se han asignado. Haga clic en la casilla **Habilitar desvío para sitios sin asignar** solamente si dispone de uno o más sitios grandes asociados con la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunos sitios de sucursal asociados con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica porque solo especifica subredes asociadas con los sitios de sucursal en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no seleccionar la casilla **Habilitar desvío para sitios sin asignar** si se ha habilitado el CAC.

8.  Haga clic en **Confirmar** para guardar los cambios.


## <a name="disable-network-media-bypass"></a>Deshabilitar la omisión de medios de red

La configuración de omisión de medios se aplica globalmente en una implementación de Skype Empresarial Server. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener más información acerca de cuándo usar la omisión de medios, vea [Planear la omisión de medios.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) Puede deshabilitar la omisión de medios desde el Panel de control de Skype Empresarial Server. 


### <a name="to-disable-media-bypass"></a>Para deshabilitar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página  **Editar configuración global**, desactive la casilla  **Habilitar desvío de medios**.

7.  Haga clic en  **Confirmar** para guardar los cambios.

  
