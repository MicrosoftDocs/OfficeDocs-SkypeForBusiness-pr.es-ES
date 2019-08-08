---
title: Implementar la supervisión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumen: Aprenda a implementar la supervisión en Skype empresarial Server.'
ms.openlocfilehash: 1eedcaaa30ecf464a5238e274e14de6770858290
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239956"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implementar la supervisión en Skype empresarial Server

**Resumen:** Aprenda a implementar la supervisión en Skype empresarial Server.

Antes de realizar estas tareas, revise [planear la supervisión en Skype empresarial Server](../../plan-your-deployment/monitoring.md).

Normalmente, implementará servicios de supervisión dentro de la topología al completar los siguientes dos pasos:

1. Habilitar la supervisión al mismo tiempo que se configura un nuevo grupo de servidores de Skype empresarial. (En Skype empresarial Server, la supervisión está habilitada o deshabilitada para cada grupo). Tenga en cuenta que puede habilitar la supervisión de un grupo sin recopilar realmente datos de supervisión, un proceso descrito en la sección configuración de la configuración de registro de detalles de llamadas y calidad de la experiencia de esta documentación.

2. Al asociar un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función de la cantidad de usuarios hospedados en los grupos de registradores, no tiene que configurar una base de datos de supervisión independiente para cada uno de los grupos. En su lugar, varios grupos de servidores pueden usar el almacén de supervisión único.

Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que aunque ya no hay un rol de servidor de supervisión, todavía tendrá que crear uno o más almacenes de supervisión: bases de datos back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 o Microsoft SQL Server 2014.

> [!NOTE]
> Si se ha habilitado la supervisión para un grupo, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar su topología: Skype empresarial Server le permite deshabilitar (y volver a habilitar más adelante) la grabación de detalles de llamadas (CDR) o la calidad de Experience (QoE) recopilación de datos. Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.

Otra mejora importante de la supervisión en Skype empresarial Server es que los informes de supervisión de Skype empresarial Server ahora son compatibles con IPv6: los informes que usan el campo dirección IP mostrarán direcciones IPv4 o IPv6, en función de: 1, la consulta SQL se está usando; y 2) donde la dirección IPv6 está almacenada en la base de datos de supervisión.

> [!NOTE]
> Asegúrese de que el tipo de inicio del servicio del Agente SQL Server sea automático y de que el servicio del Agente SQL Server se esté ejecutando para la instancia de SQL que contiene las bases de datos de supervisión, de manera que las tareas de mantenimiento predeterminadas de supervisión de SQL Server puedan ejecutarse según se programaron, bajo el control del servicio del Agente SQL Server.

Esta documentación le guiará a través del proceso de instalación y configuración de los informes de supervisión y supervisión de Skype empresarial Server. En la documentación se proporcionan instrucciones detalladas que le ayudarán a:

- Habilitar la supervisión en la topología y asociar un almacén de supervisión a un grupo de servidores front-end.

- Instale SQL Server Reporting Services y los informes de supervisión de Skype empresarial Server. Los informes de supervisión son informes previamente configurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.

- Configure el registro de detalles de llamada (CDR) y la recopilación de datos de calidad de experiencia (QoE). La grabación de detalles de llamadas le permite realizar un seguimiento del uso de las capacidades de Skype empresarial Server, como las llamadas telefónicas de voz a través de IP (VoIP); mensajería instantánea (mi); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

- Purgue de forma manual los registros de CDR o de QoE de la base de datos de supervisión.

## <a name="deployment-checklist-for-monitoring"></a>Lista de comprobación para la supervisión

Aunque la supervisión ya está instalada y activa en cada servidor front-end, hay varios pasos que debe realizar antes de que pueda recopilar datos de supervisión de Skype empresarial Server. Estos pasos se describen en la siguiente lista de comprobación:

|**Fase**|**Pasos**|**Rol y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Instale una versión compatible de Microsoft SQL Server en el equipo que actuará como almacén de datos back-end para la supervisión.  <br/> |Usuario de dominio que también es miembro del grupo de administradores locales.  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Crear la topología interna adecuada para admitir la supervisión** <br/> |Use el generador de topologías de Skype empresarial Server para agregar bases de datos de supervisión a la topología y, después, publique la topología actualizada.  <br/> |Para definir una topología, un usuario que sea miembro del grupo de usuarios locales.  <br/> Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.  <br/> |[Asociar una tienda de supervisión con un grupo de servidores front-end en Skype empresarial Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar la configuración de supervisión adecuada** <br/> |Habilitar el registro detallado de llamadas (CDR) o la supervisión de la calidad de la experiencia (QoE) en los ámbitos del sitio o a nivel global.  <br/> |Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.  <br/> |[Configurar la grabación de detalles de llamadas y la configuración de la calidad de la experiencia en Skype empresarial Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Habilitar la supervisión

Aunque los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, eso no significa que comience a recopilar datos de supervisión de forma automática en el momento de finalizar la instalación de Skype empresarial Server. En su lugar, deberá llevar a cabo dos tareas: debe asociar los servidores front-end/grupos de servidores front-end a una base de datos de supervisión y debe habilitar la supervisión del registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) en ámbito global o del sitio.

Para obtener instrucciones paso a paso sobre la Asociación de servidores front-end o grupos de aplicaciones para el usuario con una base de datos de supervisión, consulte el tema sobre cómo [asociar una tienda de supervisión con un grupo de servidores front-end en Skype empresarial Server](associate-a-monitoring-store.md) en la guía de implementación. Después de que se hayan realizado estas asociaciones y después de que se haya publicado la nueva topología de servidor de Skype empresarial, aún no podrá recopilar datos de supervisión. Esto se debe a que, de forma predeterminada, la recopilación de datos de CDR y QoE está deshabilitada al instalar Skype empresarial Server.

Para comenzar la recopilación de datos, deberá habilitar la supervisión de CDR y/o QoE. (Tenga en cuenta que no tiene que habilitar la supervisión de CDR y QoE; si lo prefiere, puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar la supervisión de CDR en el ámbito global, ejecute el siguiente comando desde el shell de administración de Skype empresarial Server:

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

También puede habilitar la supervisión de CDR desde el panel de control de Skype empresarial Server. Desde el panel de control de Skype empresarial Server, complete el siguiente procedimiento:

1. Haga clic en **Supervisión**.

2. En la pestaña **Registro detallado de llamadas**, haga doble clic en la configuración **Global**.

3. En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de CDR** y haga clic en **Confirmar**.

Para habilitar la supervisión de QoE en el ámbito global, ejecute este comando desde el shell de administración de Skype empresarial Server:

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si lo prefiere, también puede habilitar la supervisión de QoE desde el panel de control de Skype empresarial Server. Desde allí, lleve a cabo el procedimiento siguiente:

1. Haga clic en **Supervisión**.

2. En la pestaña **Datos de calidad de la experiencia**, haga doble clic en la configuración **Global**.

3. En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de QoE** y haga clic en **Confirmar**.

Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de CDR y QoE en toda la organización. De forma alternativa, puede separar las opciones de configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información sobre cómo administrar las opciones de configuración de supervisión, consulte el tema de la guía de implementación configuración de la [grabación de detalles de llamadas y de la calidad de la experiencia en Skype empresarial Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Vea también

[Planear la supervisión en Skype empresarial Server](../../plan-your-deployment/monitoring.md)
