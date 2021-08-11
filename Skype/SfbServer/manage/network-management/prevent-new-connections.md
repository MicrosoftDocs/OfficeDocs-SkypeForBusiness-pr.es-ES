---
title: Impedir nuevas conexiones
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
description: ''
ms.openlocfilehash: d62a3af74607c3f4868ed1d808160556a765844f298ec889b37137b3133d8a30
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294217"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedir nuevas conexiones a Skype Empresarial Server para el mantenimiento del servidor


Skype Empresarial Server permite desconectar un servidor (por ejemplo, aplicar actualizaciones de software o hardware) sin pérdida de servicio para los usuarios.

Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.

Cuando se impiden nuevas conexiones a un servidor front-end, algunas Skype Empresarial Server características y servicios dependen del equilibrio de carga dns para asegurarse de que funciona correctamente. Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas. Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:

  - Attendant

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación Estacionamiento de llamadas

Para obtener más información sobre el equilibrio de carga DNS, vea [Requisitos de equilibrio de carga.](../../plan-your-deployment/network-requirements/load-balancing.md)

Además de impedir nuevas conexiones para todos los servicios de un servidor que Skype Empresarial Server, también puede impedir nuevas conexiones para servicios Skype Empresarial Server individuales. Por ejemplo, este método es útil en una situación en la que debe aplicar una actualización de Skype Empresarial Server que no requiera que se cierre todo el servidor. Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows. Por ejemplo, el servicio Skype Empresarial Server Front-End y el agente de recopilación de datos para supervisión son servicios de Skype Empresarial Server independientes, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end Skype Empresarial Server. Puede evitar nuevas conexiones para el Skype Empresarial Server front-end, pero no puede evitar nuevas conexiones para estos dos servicios Skype Empresarial Server individuales por separado.

> [!IMPORTANT]
> Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para evitar nuevas conexiones a Skype Empresarial Server

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola de complemento Servicios: haga **clic** en Inicio , elija Todos los programas **,** Herramientas **administrativas** y, a continuación, haga clic en **Servicios**.

3.  En la lista, haga doble clic en Skype Empresarial Server Windows servicio al que desea evitar nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.

5.  Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.
    
    > [!IMPORTANT]
    > Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.
