---
title: Implementar la supervisión en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumen: Conozca cómo implementar supervisión en Skype para Business Server 2015.'
ms.openlocfilehash: a963db346f5d9f7904b43fc2032aa881295d1b77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-monitoring-in-skype-for-business-server-2015"></a>Implementar la supervisión en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a implementar la supervisión en Skype para Business Server 2015.
  
Normalmente, implementará servicios de supervisión dentro de la topología al completar los siguientes dos pasos:
  
1. Habilitar la supervisión de al mismo tiempo configurar un nuevo Skype para el grupo de servidores empresariales. (En Skype para Business Server 2015, supervisión está habilitada o deshabilitada en un pool por pool.) Tenga en cuenta que puede habilitar la supervisión de un grupo sin realmente recopilación de los datos de supervisión, un proceso que se explica en la sección Configurar Call Recording de detalle y la configuración de calidad de la experiencia de esta documentación.
    
2. Al asociar un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función de la cantidad de usuarios hospedados en los grupos de registradores, no tiene que configurar una base de datos de supervisión independiente para cada uno de los grupos. En su lugar, varios grupos de servidores pueden usar el almacén de supervisión único.
    
Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que aunque ya no hay un rol de servidor de supervisión, todavía tendrá que crear uno o más almacenes de supervisión: bases de datos back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 o Microsoft SQL Server 2014.
  
> [!NOTE]
> Si ha habilitado la supervisión de un grupo puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar la topología: Skype para Business Server proporciona una manera de deshabilitar (y, a continuación, volver a habilitar) llame al detalle grabación (CDR) o calidad de Recopilación de datos de experiencia (QoE). Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento. 
  
Una otra mejora importante a supervisión en Skype para Business Server 2015 es el hecho de que Skype para informes de supervisión de servidor de negocios ahora admite IPv6: informes que utilizan el campo de dirección IP mostrarán en IPv4 o IPv6 direcciones dependiendo de: 1) el SQL consulta que se utiliza; y, 2) donde o no la dirección IPv6 se almacena en la base de datos de supervisión.
  
> [!NOTE]
> Asegúrese de que el tipo de inicio del servicio del Agente SQL Server sea automático y de que el servicio del Agente SQL Server se esté ejecutando para la instancia de SQL que contiene las bases de datos de supervisión, de manera que las tareas de mantenimiento predeterminadas de supervisión de SQL Server puedan ejecutarse según se programaron, bajo el control del servicio del Agente SQL Server. 
  
Esta documentación le guiará en el proceso de instalar y configurar informes de supervisión y monitoreo de Skype para Business Server 2015. En la documentación se proporcionan instrucciones detalladas que le ayudarán a:
  
- Habilitar la supervisión en la topología y asociar un almacén de supervisión a un grupo de servidores front-end.
    
- Instalar SQL Server Reporting Services y el Skype para Business Server informes de supervisión. Los informes de supervisión son informes previamente configurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.
    
- Configure el registro de detalles de llamada (CDR) y la recopilación de datos de calidad de experiencia (QoE). Registro de detalles de llamada proporciona una manera de realizar un seguimiento del uso de Skype para las funciones de servidor de negocios como voz sobre IP (VoIP) llamadas de teléfono; mensajería instantánea (IM); transferencias de archivos; audio y vídeo (A / V) conferencia; y sesiones de uso compartido de aplicaciones. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).
    
- Purgue de forma manual los registros de CDR o de QoE de la base de datos de supervisión.
    
## <a name="deployment-checklist-for-monitoring"></a>Lista de comprobación para la supervisión

Aunque la supervisión ya está instalada y activada en cada servidor Front-End, todavía hay varios pasos que debe llevar a cabo antes de que pueda ser realmente recopilar datos de supervisión de Skype para Business Server 2015. Estos pasos se describen en la siguiente lista de comprobación:
  
|**Fase**|**Pasos**|**Función y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Instale una versión compatible de Microsoft SQL Server en el equipo que actuará como almacén de datos back-end para la supervisión.  <br/> |Usuario de dominio que también es miembro del grupo de administradores locales.  <br/> |[Hardware compatible](http://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Software de servidor e infraestructura de soporte](http://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Crear la topología interna adecuada para admitir la supervisión** <br/> |Usar Skype para el generador de topología de 2015 Business Server agregar, a continuación, monitoreo de bases de datos de la topología, publica la topología actualizados.  <br/> |Para definir una topología, un usuario que sea miembro del grupo de usuarios locales.  <br/> Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.  <br/> |[Asociar un almacén de supervisión con una agrupación de Front-End en Skype para Business Server 2015](associate-a-monitoring-store.md) <br/> |
|**Habilitar la configuración de supervisión adecuada** <br/> |Habilitar el registro detallado de llamadas (CDR) o la supervisión de la calidad de la experiencia (QoE) en los ámbitos del sitio o a nivel global.  <br/> |Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.  <br/> |[Configurar el registro de detalles de llamadas y la configuración de calidad de la experiencia en Skype para Business Server 2015](call-detail-recording-and-qoe.md) <br/> |
   
## <a name="enable-monitoring"></a>Habilitar la supervisión

Aunque los agentes de la colección de datos unificado automáticamente están instalados y activados en cada servidor Front-End, eso no significa que se iniciará automáticamente recopilar datos de supervisión en el momento en que termine de instalar Skype para Business Server 2015. En su lugar, deberá llevar a cabo dos tareas: debe asociar los servidores front-end/grupos de servidores front-end a una base de datos de supervisión y debe habilitar la supervisión del registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) en ámbito global o del sitio.
  
Para obtener instrucciones detalladas acerca de cómo asociar los servidores Front-End o grupos de servidores de Front-End con una base de datos de supervisión, consulte el tema [asociar un almacén de supervisión con una agrupación de Front-End en Skype para Business Server 2015](associate-a-monitoring-store.md) en la Guía de implementación. Después de hacer estas asociaciones, y después se ha publicado el nuevo Skype para la topología de servidores de negocios, aún no podrá recopilar datos de supervisión. Eso es porque, de forma predeterminada, recopilación de datos de CDR y QoE está deshabilitado al instalar Skype para Business Server 2015.
  
Para comenzar la recopilación de datos debe habilitar CDR o supervisión de la calidad de la experiencia. (Tenga en cuenta que no es necesario habilitar a ambos CDR y QoE supervisión; si lo prefiere, puede habilitar a un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar a CDR supervisión en la ejecución de ámbito global el siguiente comando desde dentro el Skype para el Shell de administración de servidor de negocios:
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Como alternativa, puede habilitar a CDR supervisión desde dentro el Skype para el Panel de Control de servidor empresarial. Desde dentro el Skype para el Panel de Control de servidor de negocios, complete el procedimiento siguiente:
  
1. Haga clic en **Supervisión**.
    
2. En la pestaña **Registro detallado de llamadas**, haga doble clic en la configuración **Global**.
    
3. En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de CDR** y haga clic en **Confirmar**.
    
Para habilitar QoE supervisión en el ámbito global, ejecute este comando desde dentro el Skype para el Shell de administración de servidor de negocios:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si lo prefiere, también puede habilitar QoE supervisión desde dentro el Skype para el Panel de Control de servidor empresarial. Desde allí, lleve a cabo el procedimiento siguiente:
  
1. Haga clic en **Supervisión**.
    
2. En la pestaña **Datos de calidad de la experiencia**, haga doble clic en la configuración **Global**.
    
3. En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de QoE** y haga clic en **Confirmar**.
    
Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de CDR y QoE en toda la organización. De forma alternativa, puede separar las opciones de configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información acerca de cómo administrar la configuración de supervisión, consulte el tema de la Guía de implementación [Configurar registro de detalles de llamadas y la configuración de calidad de la experiencia de Skype para Business Server 2015](call-detail-recording-and-qoe.md).
  

