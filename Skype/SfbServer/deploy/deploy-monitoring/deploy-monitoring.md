---
title: Implementar la supervisión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumen: obtenga información sobre cómo implementar la supervisión en Skype Empresarial Server.'
ms.openlocfilehash: 89474b7d40a63911c6a79bee719573516a9d423a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802280"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implementar la supervisión en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo implementar la supervisión en Skype Empresarial Server.

Antes de realizar estas tareas, revise [El plan para la supervisión en Skype Empresarial Server.](../../plan-your-deployment/monitoring.md)

Normalmente, implementará servicios de supervisión dentro de la topología completando los dos pasos siguientes:

1. Habilitar la supervisión al mismo tiempo que configura un nuevo grupo de servidores de Skype Empresarial Server. (En Skype Empresarial Server, la supervisión está habilitada o deshabilitada por grupo de servidores). Tenga en cuenta que puede habilitar la supervisión de un grupo de servidores sin recopilar realmente datos de supervisión, un proceso que se explica en la sección Configurar el registro detallado de llamadas y la configuración de calidad de la experiencia de esta documentación.

2. Asociando un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función del número de usuarios hospedados en sus grupos de servidores del registrador, eso significa que no tiene que configurar una base de datos de supervisión independiente para cada uno de sus grupos de servidores. En su lugar, el almacén de supervisión único se puede usar por varios grupos de servidores.

Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que, aunque ya no haya un rol de servidor de supervisión, tendrá que crear uno o más almacenes de supervisión: bases de datos back-end que se usan para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 o Microsoft SQL Server 2019.

> [!NOTE]
> Si la supervisión se ha habilitado para un grupo de servidores, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar la topología: Skype Empresarial Server permite deshabilitar (y volver a habilitar posteriormente) la recopilación de datos del registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE). Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.

Otra mejora importante de la supervisión en Skype Empresarial Server es el hecho de que los informes de supervisión de Skype Empresarial Server ahora admiten IPv6: los informes que usan el campo Dirección IP mostrarán direcciones IPv4 o IPv6 en función de : 1) la consulta SQL que se use; y, 2) donde o no se almacena la dirección IPv6 en la base de datos de supervisión.

> [!NOTE]
> Asegúrese de que el tipo de inicio del servicio de agente de SQL Server es Automático y de que el servicio de agente de SQL Server se está ejecutando para la instancia de SQL que tiene las bases de datos de supervisión, de modo que los trabajos de mantenimiento de SQL Server de supervisión predeterminados se puedan ejecutar de forma programada bajo el control del servicio de agente de SQL Server.

Esta documentación le guiará por el proceso de instalación y configuración de informes de supervisión y supervisión para Skype Empresarial Server. La documentación proporciona instrucciones detalladas que le ayudarán a:

- Habilitar la supervisión en su topología y asociar un almacén de supervisión a un grupo de servidores front-end.

- Instale SQL Server Reporting Services y los informes de supervisión de Skype Empresarial Server. Los informes de supervisión son informes preconfigurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.

- Configurar el registro detallado de llamadas (CDR) y la recopilación de datos de calidad de la experiencia (QoE). El registro detallado de llamadas permite realizar un seguimiento del uso de funcionalidades de Skype Empresarial Server, como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (MI); transferencias de archivos; conferencia de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

- Depure manualmente los registros de CDR y/o QoE de la base de datos de supervisión.

## <a name="deployment-checklist-for-monitoring"></a>Lista de comprobación de implementación para supervisión

Aunque la supervisión ya está instalada y activada en cada servidor front-end, todavía hay varios pasos que debe realizar antes de poder realmente recopilar datos de supervisión para Skype Empresarial Server. Estos pasos se describen en la siguiente lista de comprobación:

|**Fase**|**Pasos**|**Pertenencia a grupos y funciones**.|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar el hardware y el software necesario como requisito previo** <br/> |Instalar una versión compatible de Microsoft SQL Server en el PC que actuará como almacén de datos back-end para la supervisión.  <br/> |Usuario de dominio que también es miembro del grupo de administradores locales  <br/> |[Hardware admitido](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Software de servidor y compatibilidad con la infraestructura](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Crear la topología interna adecuada para admitir la supervisión** <br/> |Use el Generador de topologías de Skype Empresarial Server para agregar bases de datos de supervisión a la topología y, a continuación, publique la topología actualizada.  <br/> |Para definir una topología, un usuario que sea miembro del grupo de usuarios locales  <br/> Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.  <br/> |[Asociar un almacén de supervisión con un grupo de servidores front-end en Skype Empresarial Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar la configuración de supervisión adecuada** <br/> |Habilite el registro detallado de llamadas (CDR) o la supervisión de calidad de la experiencia (QoE) en los ámbitos global o de sitio.  <br/> |Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.  <br/> |[Configurar el registro detallado de llamadas y la calidad de la experiencia en Skype Empresarial Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Habilitar supervisión

Aunque los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end, esto no significa que comience automáticamente a recopilar datos de supervisión en el momento en que termine de instalar Skype Empresarial Server. En su lugar, debe hacer dos cosas: debe asociar los servidores front-end/grupos de servidores front-end con una base de datos de supervisión y debe habilitar el registro detallado de llamadas (CDR) o la supervisión de calidad de la experiencia (QoE) en el ámbito global o en el ámbito de sitio.

Para obtener instrucciones paso a paso sobre cómo asociar servidores front-end o grupos de servidores front-end con una base de datos de supervisión, consulte el tema Asociar un almacén de supervisión con un grupo de servidores front-end en [Skype Empresarial Server](associate-a-monitoring-store.md) en la guía de implementación. Una vez realizadas estas asociaciones y después de publicar la nueva topología de Skype Empresarial Server, aún no podrá recopilar datos de supervisión. Esto se debe a que, de forma predeterminada, la recopilación de datos de CDR y QoE está deshabilitada al instalar Skype Empresarial Server.

Para iniciar la recopilación de datos, deberá habilitar la supervisión de CDR o QoE. (Tenga en cuenta que no es necesario habilitar la supervisión de CDR y QoE; si lo prefiere, puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar la supervisión de CDR en el ámbito global, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Como alternativa, puede habilitar la supervisión de CDR desde el Panel de control de Skype Empresarial Server. Desde el Panel de control de Skype Empresarial Server, realice el siguiente procedimiento:

1. Haga clic en **Supervisión**.

2. En la pestaña **Registro detallado de llamadas**, haga doble clic en **Global**.

3. En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de registros detallados de llamadas (CDR)** y haga clic en **Confirmar**.

Para habilitar la supervisión de QoE en el ámbito global, ejecute este comando desde el Shell de administración de Skype Empresarial Server:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si lo prefiere, también puede habilitar la supervisión de QoE desde el Panel de control de Skype Empresarial Server. Desde el Panel de control, lleve a cabo el procedimiento siguiente:

1. Haga clic en **Supervisión**.

2. En la pestaña **Datos de calidad de la experiencia**, haga doble clic en **Global**.

3. En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** y haga clic en **Confirmar**.

Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de datos de CDR y QoE en la organización. De forma alternativa, puede separar la configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de datos de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información sobre cómo administrar las opciones de configuración de supervisión, consulte el tema de la guía de implementación Configurar el registro detallado de llamadas y la configuración de calidad de la experiencia [en Skype Empresarial Server.](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>Vea también

[Planear la supervisión en Skype Empresarial Server](../../plan-your-deployment/monitoring.md)
