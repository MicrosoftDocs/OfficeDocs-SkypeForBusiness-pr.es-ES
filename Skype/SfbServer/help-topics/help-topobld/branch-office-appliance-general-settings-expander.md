---
title: Expansor de configuración general de aplicación de sucursal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar la configuración de una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, dispone de las secciones siguientes:'
ms.openlocfilehash: 5c8791661ff32c6cb40b968297d11595f5873bcf0b1cf0ce50078e41e713d68a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277005"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de configuración general de aplicación de sucursal

Para editar la configuración de una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, dispone de las secciones siguientes:

- Configuración general

- Configuración de resistencia

- Configuración del servidor de mediación



Para una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, cuenta con lo siguiente:

## <a name="general-settings"></a>Configuración general

El nombre de dominio completo (FQDN) de la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia. Edite el FQDN del servidor para cambiar el valor. Debe tener un registro de host (A) del sistema de nombres de dominio (DNS) que coincida con el valor nuevo.

Puede seleccionar **Usar todas las direcciones IP configuradas** o **Limitar el uso de servicio a las direcciones IP seleccionadas**. Si selecciona **Limitar el uso de servicio a las direcciones IP seleccionadas**, definirá la dirección IP principal que utilizará el servidor para todas las comunicaciones excepto para la puerta de enlace de la red de telefonía conmutada (RTC). Defina otra dirección IP para la RTC.

En **Asociaciones**, puede editar o especificar lo siguiente:

- Asociar servidor de archivado permite seleccionar asociar un servidor de archivado con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia. Para seleccionar un servidor de archivado ya definido, seleccione el servidor en  la lista desplegable o haga clic en Nuevo para especificar un nuevo servidor de archivado.

    > [!IMPORTANT]
    > Antes de publicar la topología recién definida, el servidor que especifique debe existir y se debe unir en el dominio.

- Asociar servidor de supervisión permite seleccionar asociar un servidor de supervisión con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia. Para seleccionar un servidor de supervisión ya definido, seleccione el servidor de  la lista desplegable o haga clic en Nuevo para especificar un nuevo servidor de supervisión.

- Asociar grupo de servidores perimetrales permite seleccionar asociar un servidor perimetral o grupo de servidores con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia. Puede seleccionar un servidor perimetral o un grupo de servidores perimetrales que ya estén definidos seleccionándolos en la lista desplegable o hacer clic en **Nuevo** para especificar un servidor perimetral o grupo de servidores perimetrales nuevo.

## <a name="resiliency"></a>Resistencia

La resistencia proporciona una gran disponibilidad al grupo de registradores. Al proporcionar un registrador de copia de seguridad, si el primer registrador falla, el registrador de copia de seguridad puede reemplazar al que ha fallado de modo que los usuarios puedan seguir registrándose y comunicándose. Es posible que algunos usuarios tengan una funcionalidad reducida según los sistemas que hayan fallado con el registrador principal.

En la lista desplegable, seleccione el grupo de servidores front-end Enterprise Edition o el servidor front-end de Standard Edition que actuará como registrador de copia de seguridad para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia. También puede habilitar intervalos de tiempo de la conmutación por error y conmutación por recuperación. Al habilitar la configuración de tiempo de la conmutación por error y la conmutación por recuperación (especificada en segundos) se habilita la detección automática de los registradores erróneos, y el tiempo de conmutación por recuperación que permite la determinación automática que el principal vuelve a estar recuperado y puede retomar el proceso del registrador.

> [!IMPORTANT]
> Al definir la detección de fallos y el intervalo de conmutación por recuperación, tenga mucho cuidado de no introducir un intervalo que provoque la ejecución de la conmutación por error y por recuperación en el caso que el registrador no logre responder durante un espacio breve de tiempo. Es posible que el registrador principal no responda durante breves periodos de tiempo en función de la carga de los grupos o servidores. Los valores predeterminados para una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en un sitio a un grupo o servidor front-end de Standard Edition son 120 segundos para la conmutación por error y 240 segundos para la reserva.

## <a name="mediation-server"></a>Servidor de mediación

Para **Servidor de mediación** puede especificar lo siguiente:

La casilla de verificación **Servidor de mediación combinado habilitado** no está disponible en una Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia porque el servidor de mediación está combinado.

Defina el puerto de escucha de los servidores del grupo para la Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación combinado. Esta configuración es opcional y debería consultar los requisitos de su puerta de enlace o de la RTC para determinar si la necesita. De forma predeterminada, el valor del puerto TCP es 5068.

Defina las puertas de enlace de la RTC que están asociadas con el servidor de mediación combinado. Si ya ha definido puertas de enlace, éstas se podrán asociar con el servidor de mediación. Si no a definido ninguna puerta de enlace, pero las tiene disponibles para definirlas, puede seleccionar **Nuevo**. También puede quitar puertas de enlace que ya estén configuradas para este servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en **Quitar**.

Si tiene más de una puerta de enlace asociada con el servidor de mediación, la primera puerta de enlace asociada será la predeterminada. Si debe elegir otra puerta de enlace como predeterminada, seleccione la que desee y, a continuación, haga clic en **Convertir en predeterminada**.

## <a name="see-also"></a>Consulte también

Para más información sobre cómo definir y configurar la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia, consulte [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).