---
title: Prevención de nuevas conexiones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279490"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Prevención de nuevas conexiones a Skype empresarial Server para el mantenimiento del servidor


Skype empresarial Server le permite poner un servidor fuera de línea (por ejemplo, para aplicar actualizaciones de software o hardware) sin ninguna pérdida de servicio para los usuarios.

Cuando especifica la opción de evitar nuevas conexiones o llamadas a un servidor de un grupo, deja de tomarse cualquier conexión y llamada nuevas tan pronto como implemente esta opción. Estas nuevas conexiones y llamadas se enrutan a través de otros servidores del grupo. Un servidor que impide nuevas conexiones permite que las sesiones de las conexiones existentes continúen hasta que se desordenan de forma natural. Cuando haya finalizado todas las sesiones existentes, el servidor estará listo para desconectarse.

Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Skype empresarial Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente. Si no usa el equilibrio de carga de DNS en el grupo, es posible que las conexiones a través de estos servicios no se redirijan a otros servidores durante el período en el que el servidor está impidiendo las conexiones nuevas y, por lo tanto, cuando el servidor se desconecta, algunas sesiones y llamadas pueden ser interrupción. Las características que dependen del equilibrio de carga de DNS para asegurarse de que esta opción funciona correctamente son las siguientes:

  - Operador

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación de estacionamiento de llamadas

Para obtener más información sobre el equilibrio de carga de DNS, consulte [requisitos de equilibrio de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

Además de impedir nuevas conexiones para todos los servicios en un servidor con Skype empresarial Server, también puede evitar nuevas conexiones para servicios individuales de Skype empresarial Server. Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Skype empresarial Server que no requiera que se cierre todo el servidor. Tenga en cuenta que cuando impide las conexiones para un servicio, debe seleccionar un servicio tal como está agrupado y se muestra en la lista de servicios de Windows. Por ejemplo, el servicio front-end de Skype empresarial Server y el agente de recopilación de datos para la supervisión son servicios independientes de Skype empresarial, pero en la lista de servicios de Windows se consolidan y se muestran como el front-end de Skype empresarial Server. Service. Puede evitar nuevas conexiones para el servicio de front-end de Skype empresarial Server, pero no puede evitar nuevas conexiones por separado para estos dos usuarios de servicios de Skype empresarial subyacentes.

> [!IMPORTANT]
> Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie. Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para evitar nuevas conexiones a Skype empresarial Server

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.

3.  En la lista, haga doble clic en el servicio de Windows de Skype empresarial Server en el que desea evitar nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: iniciado**, haga clic en pausar. ****

5.  De forma opcional, pero recomendado, junto a **tipo de inicio**, haga clic en **manual**.
    
    > [!IMPORTANT]
    > Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie. Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.
