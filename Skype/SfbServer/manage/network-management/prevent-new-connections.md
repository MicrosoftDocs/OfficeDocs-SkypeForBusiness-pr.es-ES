---
title: Impedir nuevas conexiones
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889729"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedir nuevas conexiones a Skype para Business Server para el mantenimiento del servidor


Skype para Business Server le permite desconectar un servidor sin conexión (por ejemplo, para aplicar las actualizaciones de software o hardware) sin ninguna pérdida de servicio a los usuarios.

Cuando se especifica la opción para impedir nuevas conexiones o las llamadas a un servidor en un grupo de servidores, se detiene teniendo cualquier nuevas conexiones y llamadas tan pronto como implementar esta opción. Estas nuevas conexiones y las llamadas se enrutan a través de otros servidores del grupo de servidores. Un servidor que es impedir nuevas conexiones permite que sus sesiones en conexiones existentes para continuar hasta que finalicen con naturalidad. Cuando hayan finalizado todas las sesiones existentes, el servidor está listo para consultarse sin conexión.

Al impedir nuevas conexiones a un servidor Front-End, algunas Skype para las características de Business Server y servicios se basan en la carga de DNS para asegurarse de que funciona correctamente. Si no se usa en el grupo de servidores de equilibrio de carga DNS, las conexiones a través de estos servicios no estén desviarse a otros servidores durante el período que impide nuevas conexiones, en el servidor y, por tanto, cuando el servidor se desconecta algunas sesiones y las llamadas pueden no estar interrumpido. Las características que se basan en la carga de DNS para asegurarse de que esta opción funcione correctamente son los siguientes:

  - Operador

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación de estacionamiento de llamadas

Para obtener más información acerca de equilibrio de carga de DNS, vea [requisitos de equilibrio de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Skype para Business Server, también puede evitar nuevas conexiones para Skype individual para los servicios de servidor empresarial. Por ejemplo, este método es útil en una situación donde necesita aplicar un Skype para actualización del servidor de negocio que no requieren todo el servidor para que se apague. Tenga en cuenta que cuando se impide las conexiones para un servicio, debe seleccionar un servicio tal y como se agrupan y se muestra en la lista de servicios de Windows. Por ejemplo, la Skype para servicio Business Server front-end y el agente de recopilación de datos de supervisión son Skype independiente para servicios de Business Server, pero en la lista de servicios de Windows se consolidan y se muestra como el Skype para profesionales de servidor Front-End servicio. Puede impedir nuevas conexiones para el Skype para servicio de negocio de servidor Front-End, pero no se pueden impedir nuevas conexiones para estos dos Skype subyacente individuales para servicios de Business Server por separado.

> [!IMPORTANT]
> Cuando se establece un servidor para impedir nuevas conexiones y, a continuación, reinicie el servidor, de forma predeterminada el servidor inmediatamente empezará a aceptar nuevas conexiones después de que se inicie. Para evitarlo, establecer el servidor sólo pausar y reanudar de forma manual, antes de reiniciar el servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para impedir nuevas conexiones a Skype para Business Server

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: haga clic en **Inicio**, elija **Todos los programas**, elija **Herramientas administrativas**y, a continuación, haga clic en **Servicios**.

3.  En la lista, haga doble clic en el Skype para servicio empresarial del servidor Windows a la que desea impedir nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **estado del servicio: iniciado**, haga clic en **Pausar**.

5.  De forma opcional, pero recomendado, junto a **tipo de inicio**, haga clic en **Manual**.
    
    > [!IMPORTANT]
    > Cuando se establece un servidor para impedir nuevas conexiones y, a continuación, reinicie el servidor, de forma predeterminada el servidor inmediatamente empezará a aceptar nuevas conexiones después de que se inicie. Para evitarlo, establecer el servidor sólo pausar y reanudar de forma manual, antes de reiniciar el servidor.
