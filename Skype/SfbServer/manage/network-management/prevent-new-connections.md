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
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823470"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedir nuevas conexiones a Skype Empresarial Server para el mantenimiento del servidor


Skype Empresarial Server le permite desconectar un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin pérdida de servicio para los usuarios.

Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.

Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Skype Empresarial Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente. Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas. Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:

  - Attendant

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación Estacionamiento de llamadas

Para obtener más información sobre el equilibrio de carga de DNS, consulte [Requisitos de equilibrio de carga.](../../plan-your-deployment/network-requirements/load-balancing.md)

Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Skype Empresarial Server, también puede evitar nuevas conexiones para servicios individuales de Skype Empresarial Server. Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Skype Empresarial Server que no requiere que se cierre todo el servidor. Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows. Por ejemplo, el servicio de Front-End de Skype Empresarial Server y el agente de recopilación de datos para la supervisión son servicios independientes de Skype Empresarial Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Skype Empresarial Server. Puede evitar nuevas conexiones para el servicio front-end de Skype Empresarial Server, pero no puede evitar nuevas conexiones para estos dos servicios de Skype Empresarial Server subyacentes individuales por separado.

> [!IMPORTANT]
> Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para evitar nuevas conexiones a Skype Empresarial Server

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: **Haga** clic en Inicio , seleccione Todos los **programas,** seleccione Herramientas administrativas **y,** a continuación, haga clic en **Servicios.**

3.  En la lista, haga doble clic en el servicio de Windows de Skype Empresarial Server al que desea impedir nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.

5.  Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.
    
    > [!IMPORTANT]
    > Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.
