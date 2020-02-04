---
title: Expansor de configuración general de aplicación de sucursal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de una sucursal existente o de un servidor de sucursal que sea reviviente, se le presentarán las siguientes secciones:'
ms.openlocfilehash: 97f12828a8513ce284f4cd14c06de3496100c313
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702395"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de configuración general de aplicación de sucursal

Para editar la configuración de una sucursal existente o de un servidor de sucursal que sea reviviente, se le presentarán las siguientes secciones:

- Configuración general

- Configuración de resistencia

- Configuración del servidor de mediación


Para una sucursal o un servidor de sucursal con la supervivencia, se le presenta lo siguiente:

### <a name="general-settings"></a>Configuración general

El nombre de dominio completo (FQDN) del equipo de sucursal o del servidor de sucursal que sea reviviente. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.

Puede seleccionar **Usar todas las direcciones IP configuradas** o **Limitar el uso del servicio a las direcciones IP seleccionadas**. Si selecciona **Limitar el uso del servicio a las direcciones IP seleccionadas**, definirá la dirección IP principal que el servidor usará para todas las comunicaciones, excepto para la puerta de enlace de la red de telefonía conmutada (RTC). Para la RTC se define otra dirección IP.

En **Asociaciones**, puede editar o especificar lo siguiente:

- Asociar el servidor de archivado le permite seleccionar la Asociación de un servidor de archivado con el equipo de sucursal o el servidor de sucursal superviviente. Puede seleccionar de un servidor de archivado ya definido seleccionando el servidor de la lista desplegable o hacer clic en **nuevo** para especificar un nuevo servidor de archivado.

    > [!IMPORTANT]
    > Antes de publicar la topología recién definida, el servidor que especifique tiene que existir y estar unido al dominio.

- El servidor de supervisión asociado le permite seleccionar la Asociación de un servidor de supervisión con el equipo de la sucursal o el servidor de sucursal superviviente. Puede seleccionar uno de los servidores de supervisión ya definidos seleccionando el servidor en la lista desplegable o hacer clic en **nuevo** para especificar un nuevo servidor de supervisión.

- Asociar grupo Edge le permite seleccionar asociar un servidor perimetral o un grupo de servidores a la sucursal o servidor de sucursal superviviente. Puede elegir un servidor perimetral o un grupo de servidores perimetrales que ya esté definido seleccionándolo en la lista desplegable o hacer clic en **Nuevo** para especificar un servidor perimetral o grupo de servidores perimetrales nuevo.

### <a name="resiliency"></a>Resistencia

La resistencia proporciona una gran disponibilidad al grupo de registradores. Al proporcionar un registrador de copia de seguridad, si el primer registrador falla, el registrador de copia de seguridad puede reemplazar al que ha fallado de modo que los usuarios puedan seguir registrándose y comunicándose. Es posible que algunos usuarios tengan una funcionalidad reducida según los sistemas que hayan fallado con el registrador principal.

En la lista desplegable, seleccione el grupo de servidores front-end de Enterprise Edition o el servidor front-end Standard Edition que actuará como registrador de copias de seguridad de la aplicación de sucursales que es modificable o el servidor de sucursal con la supervivencia. También puede habilitar intervalos de tiempo de conmutación por error y conmutación por recuperación. Al habilitar la configuración de tiempo de conmutación por error y la conmutación por recuperación (lo que se especifica en segundos), se habilita la detección automática de registradores erróneos y un tiempo de conmutación por recuperación que permite la determinación automática que el registrador principal vuelve a estar recuperado y puede retomar el proceso del registrador.

> [!IMPORTANT]
> Al definir la detección de fallos y el intervalo de conmutación por recuperación, tenga mucho cuidado de no introducir un intervalo que provoque la ejecución de la conmutación por error y por recuperación en el caso que el registrador no logre responder durante un espacio breve de tiempo. Es posible que el registrador principal no responda durante breves periodos de tiempo en función de la carga de los grupos o servidores. Los valores predeterminados para un equipo de sucursal con capacidad de supervivencia o un servidor de sucursal que se pueda realizar en un sitio a un grupo de servidores front-end Standard Edition son 120 segundos para la conmutación por error y 240 segundos para la reserva.

### <a name="mediation-server"></a>Servidor de mediación

Puede especificar lo siguiente en relación con un **servidor de mediación**:

La casilla de verificación para el **servidor de mediación activada** no está disponible en una aplicación de sucursal o servidor de sucursal superviviente, porque el servidor de mediación está en el mismo lugar.

Defina el puerto de escucha de los servidores del grupo para Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesitará definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.

Las puertas de enlace RTC se definen con el servidor de mediación de anuncios. Si ya ha definido las puertas de enlace, estarán disponibles para asociarlas con el servidor de mediación. Si no ha definido ninguna puerta de enlace, pero hay disponibles para definirlas, puede seleccionar **Nuevo**. También puede quitar las puertas de enlace que ya están configuradas para este servidor de mediación. Seleccione la puerta de enlace y, luego, haga clic en **Quitar**.

Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la predeterminada. Si tiene que elegir otra puerta de enlace como predeterminada, seleccione la que quiera y, luego, haga clic en **Establecer como predeterminado**.


Para obtener detalles acerca de la definición y configuración de la configuración de la aplicación de sucursal o servidor de sucursal supervivientes, consulte [soluciones de resistencia para sitios de sucursales](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


