---
title: Expansor de configuración general front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Para editar la configuración de un grupo de servidores front-end o un servidor Standard Edition, cuenta con las secciones siguientes:'
ms.openlocfilehash: 6f66fadbc722f59bdc7bcb54b149bf05fa322afb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215511"
---
# <a name="front-end-general-settings-expander"></a>Expansor de configuración general front-end

Para editar la configuración de un grupo de servidores front-end o un servidor Standard Edition, cuenta con las secciones siguientes:

- Configuración general

- Configuración de la resistencia

- Configuración de servicios web

- Configuración del servidor de mediación

## <a name="front-end-pool"></a>Grupo de servidores front-end

Para un grupo de servidores front-end, puede configurar las opciones generales, de resistencia, servicios web y servidor de mediación. Para más información, consulte las subsecciones siguientes. Para obtener más información sobre la definición y configuración de opciones para el grupo de servidores front-end, consulte [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Configuración general

Puede configurar la siguiente configuración general:

- **FQDN**. Edite el nombre de dominio completo del grupo de servidores para cambiarlo.

- **Habilitar puerto de supervisión del equilibrador de carga de hardware**. Seleccione la casilla e indique el número de puerto que usará el equilibrador de carga de hardware para supervisar el estado de los servidores del grupo de servidores.

- En **Características y funciones**, defina los roles adicionales que desea combinar con este grupo de servidores. Puede configurar las siguientes opciones:

  - **Conferencia**. Incluye compartir recursos de audio, vídeo y aplicaciones. Tras seleccionar esta opción, puede elegir conferencia de acceso telefónico (RTC). Posteriormente, en la subsección “Configuración de servidor de mediación” que aparece aquí, puede especificar y definir una puerta de enlace de RTC.

  - **Telefonía IP empresarial**. Permite llamadas de voz sobre IP internas a auriculares y dispositivos cualificados y a clientes de Skype empresarial. Para habilitar las funciones de llamadas externas, debe incluir un servidor de mediación. Para obtener más información, consulte la subsección “Configuración de servidor de mediación” que aparece más adelante en este tema.

- En **Asociaciones**, edite o especifique lo siguiente:

  - **Almacén SQL**. Modifique una base de datos de SQL Server o cree una nueva base de datos basada en SQL Server que hospede las bases de datos de grupos de servidores front-end. Puede seleccionar una nueva instancia de SQL Server en la lista o crear una entrada haciendo clic en **Nuevo**.

    Seleccione **Habilitar la creación de reflejo del almacén de SQL Server** y, a continuación, seleccione el servidor que se debe usar para la creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server nuevo.

    Seleccione **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** para seleccionar un servidor para usarlo como testigo de reflejo. Haga clic en **Nuevo** para crear un nuevo almacén de SQL Server.

  - **Recurso compartido de archivos**. Modifique el almacén de archivos usado por el grupo de servidores front-end. En la lista, puede seleccionar un nuevo almacén de archivos entre los que ya estén definidos. También puede crear un almacén de archivos haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado debe existir y estar incorporado en el dominio.

  - **Archivado**. Asocie un almacén de servidor de archivado con el grupo de servidores front-end. En la lista desplegable, puede seleccionar un almacén de SQL Server de archivado que ya esté definido o bien hacer clic en **Nuevo** para especificar un nuevo servidor de archivado.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado debe existir y estar incorporado en el dominio.

    Seleccione **Habilitar la creación de reflejo del almacén de SQL Server** y, a continuación, seleccione el servidor que se debe usar para la creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server nuevo.

    Seleccione **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** para seleccionar un servidor para usarlo como testigo de reflejo. Haga clic en **Nuevo** para crear un nuevo almacén de SQL Server.

  - **Supervisión (métricas de CDR y QoE)**. Seleccione esta opción para asociar un almacén de SQL Server de supervisión con el grupo de servidores front-end. En la lista, puede seleccionar un servidor de supervisión que ya esté definido o bien hacer clic en **Nuevo** para especificar un servidor de supervisión nuevo.

    Seleccione **Habilitar la creación de reflejo del almacén de SQL Server** y, a continuación, seleccione el servidor que se debe usar para la creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server nuevo.

    Seleccione **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** para seleccionar un servidor para usarlo como testigo de reflejo. Haga clic en **Nuevo** para crear un nuevo almacén de SQL Server.

  - **Asociar grupo de servidores perimetrales (para componentes multimedia)**. Asocie un servidor o un grupo de servidores perimetrales con el grupo de servidores front-end. En la lista, puede seleccionar un servidor o un grupo de servidores perimetrales que ya estén definidos o bien hacer clic en **Nuevo** para especificar un nuevo servidor o un nuevo grupo de servidores perimetrales.

  - **Asociar grupo con un servidor de Office Web Apps**. Seleccione esta opción para asociar un servidor de Office Web Apps con el grupo de servidores front-end. Seleccione un servidor existente en la lista o haga clic en **Nuevo** para crear un nuevo servidor de Office Web Apps.

### <a name="resiliency"></a>Resistencia

La opción Resistencia brinda recuperación ante desastres y alta disponibilidad al grupo de servidores. Al proporcionar una reserva, en caso de error en el servidor principal, puede usarse el de reserva para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el servidor principal, los usuarios pueden llegar a tener un uso restringido de las funciones.

En la lista, seleccione el grupo de servidores front-end o el servidor Standard Edition que funcionará como servidor de reserva del grupo de servidores. También puede seleccionar habilitar los intervalos de tiempo de conmutación por error y por recuperación. Habilitar la configuración de la conmutación por error y la conmutación por recuperación (en segundos) permite detectar automáticamente un servidor defectuoso; asimismo, el tiempo de recuperación permite determinar automáticamente que el servidor principal tiene una reserva.

> [!IMPORTANT]
> Al definir el intervalo de detección de errores y el de detección de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva si durante un periodo de tiempo breve se produce un error en el servidor. Es posible que el servidor principal no responda durante periodos breves, según la carga de los servidores o el grupo de servidores. Los valores predeterminados de conmutación por error y de reserva son de 300 segundos y 600 segundos de grupo de servidores a grupo de servidores, o de grupo de servidores a servidor Standard Edition. En el caso de una aplicación o servidor de sucursal con funciones de supervivencia de un sitio a un grupo de servidores o un servidor Standard Edition, el valor predeterminado es de 120 segundos para conmutación por error y 240 segundos para reserva.

> [!CAUTION]
> El valor mínimo para el **intervalo de conmutación por error** no debe ser inferior a 90 segundos. Cuando se define un valor inferior a 90 segundos, se usa el valor de 90 segundos. El tiempo de ping entre clústeres es de 30 segundos, y cuando se establece en menos de 90 puede dar como resultado un problema en el que los servidores principales y de reserva comienzan un ciclo ascendente y descendente, lo que afecta a la producción a medida que los servidores intentan resolver el estado viable del otro. Son necesarios al menos 90 segundos para determinar si el servidor principal realmente está disponible.

### <a name="web-services"></a>Servicios web

Para editar o especificar opciones adicionales de los servicios web en el grupo de servidores front-end, modifique o especifique los valores en **Servicios Web internos** y **Servicios Web externos**.

En **Servicios Web internos**, especifique lo siguiente:

> [!CAUTION]
> Si tiene más de un grupo front-end o servidor front-end, el FQDN de servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

- Si selecciona **FQDN de reemplazo**, puede especificar un nombre de dominio completo distinto para la identidad de los servicios **web internos** en el grupo de servidores. La configuración predeterminada es el nombre del grupo de servidores actual, según se haya definido para el grupo de servidores front-end.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 80 para HTTP y puerto 443 para HTTPS son los más habituales; en general, no hace falta cambiarlos a menos que la organización o el diseño de la infraestructura presenten unos requisitos concretos.

En **Servicios Web externos**, especifique lo siguiente:

- El FQDN de los servicios web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 8080 para HTTP y puerto 4443 para HTTPS se definen al principio. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Los valores predeterminados de puertos publicados se definen en puerto 80 para HTTP y puerto 443 para HTTPS. Estos valores determinan los puertos que el grupo de servidores escuchará para solicitudes entrantes. Normalmente, no es necesario cambiar estos, a menos que haya un conflicto de requisitos de puerto en el grupo de servidores. Se esperan los puertos publicados internos y externos que usen los mismos valores de puerto. Esto no es un conflicto.

### <a name="mediation-server"></a>Servidor de mediación

En **Servidor de mediación**, especifique lo siguiente:

- Si está combinando el servidor de mediación con el grupo de servidores, active la casilla **Servidor de mediación combinado habilitado**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.

- Si habilita la combinación del servidor de mediación, el intervalo de puertos de escucha del servidor en los servidores del grupo debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. De forma predeterminada, el valor de este puerto es 5068.

- Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

- Si tiene asociado más de un tronco con un servidor de mediación, puede especificar un tronco como predeterminado. Para ello, haga clic en la puerta de enlace y, a continuación, haga clic en **Convertir en predeterminada**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.

Para obtener más detalles sobre cómo definir y configurar las opciones del grupo de servidores front-end, consulte [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Servidor Standard Edition

En el caso de los servidores Standard Edition, puede configurar las opciones generales, de resistencia, de servicios web y del servidor de mediación. Para obtener información, consulte las subsecciones siguientes. Para más información sobre la definición y configuración de opciones para el servidor Standard Edition, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Configuración general

Puede configurar la siguiente configuración general:

- **FQDN**. El valor del nombre de dominio completo no se puede modificar. Debe quitarlo y redefinir el servidor Standard Edition para cambiar el nombre de dominio completo asociado con él.

- Seleccione **Usar todas las direcciones IP configuradas** o **Limitar el uso del servicio a las direcciones IP seleccionadas**. Si selecciona limitar el servicio a las direcciones IP definidas, debe definir la dirección IP principal que el servidor usará para todas las comunicaciones excepto RTC. Defina una dirección IP aparte para RTC. También puede seleccionar **Habilitar IPv6** para habilitar IPv6 para este servidor.

- **Habilitar puerto de supervisión del equilibrador de carga de hardware**. Seleccione la casilla e indique el número de puerto que usará el equilibrador de carga de hardware para supervisar el estado del servidor.

- En **Características y funcionalidad**, defina los roles adicionales que desea combinar con este servidor. Puede configurar las siguientes opciones:

  - **Conferencia**. Incluye compartir recursos de audio, vídeo y aplicaciones. Tras seleccionar esta opción, puede elegir **conferencia de acceso telefónico (RTC)**. Posteriormente, en la configuración del servidor de mediación puede especificar y definir una puerta de enlace de RTC.

  - **Telefonía IP empresarial**. Permite llamadas de voz sobre IP internas a auriculares y dispositivos cualificados y a clientes de Skype empresarial. Para habilitar las funciones de llamadas externas, debe incluir un servidor de mediación. Para obtener más información, consulte la subsección “Configuración de servidor de mediación” que aparece más adelante en este tema.

- En **Asociaciones** puede modificar o especificar lo siguiente:

  - Seleccione **Almacén de SQL Server** para asociar un almacén de SQL Server con el servidor front-end. También puede habilitar la creación de reflejo y seleccionar un servidor testigo de reflejo.

  - **Recurso compartido de archivos**. Permite modificar el almacén de archivos usado por el servidor Standard Edition. En la lista, puede seleccionar un nuevo almacén de archivos entre los que ya estén definidos. Puede crear un almacén de archivos haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado debe existir y estar incorporado en el dominio.

  - **Archivado**. Asocie un almacén de SQL Server de archivado con el servidor Standard Edition. En la lista, puede seleccionar un almacén de archivado que ya esté definido o bien hacer clic en **Nuevo** para especificar un nuevo almacén de archivado.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado debe existir y estar incorporado en el dominio.

  - **Supervisión (métricas de CDR y QoE)**. Asocie un almacén de SQL Server de supervisión con el servidor Standard Edition. En la lista, puede seleccionar un servidor de supervisión que ya esté definido o bien hacer clic en **Nuevo** para especificar un nuevo servidor de supervisión.

  - **Asociar grupo con un servidor de Office Web Apps**. Seleccione esta opción para asociar un servidor de Office Web Apps con el grupo de servidores front-end. Seleccione un servidor existente en la lista o haga clic en **Nuevo** para crear un nuevo servidor de Office Web Apps4.

  - **Grupo de servidores perimetrales asociados**. Asocie un servidor o un grupo de servidores perimetrales con el servidor Standard Edition. En la lista, puede seleccionar un servidor o un grupo de servidores perimetrales que ya estén definidos o bien hacer clic en **Nuevo** para especificar un nuevo servidor o un nuevo grupo de servidores perimetrales.

### <a name="resiliency"></a>Resistencia

La opción Resistencia brinda recuperación ante desastres y alta disponibilidad al grupo de servidores. Al proporcionar una reserva, en caso de error en el servidor principal, puede usarse el de reserva para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el servidor principal, los usuarios pueden llegar a tener un uso restringido de las funciones.

En la lista, seleccione el grupo de servidores front-end o el servidor Standard Edition que funcionará como servidor de reserva del servidor. También puede seleccionar habilitar los intervalos de tiempo de conmutación por error y por recuperación. Habilitar la configuración de la conmutación por error y la conmutación por recuperación (en segundos) permite detectar automáticamente un registrador defectuoso; asimismo, el tiempo de recuperación permite determinar automáticamente que el principal tiene una reserva.

> [!IMPORTANT]
> Al definir el intervalo de detección de errores y el de detección de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva si durante un periodo de tiempo breve se produce un error en el servidor. Es posible que el servidor principal no responda durante periodos breves, según la carga de los servidores o el grupo de servidores. Los valores predeterminados de conmutación por error y de reserva son de 300 segundos y 600 segundos de grupo de servidores a grupo de servidores, o de grupo de servidores a servidor Standard Edition. En el caso de una aplicación o servidor de sucursal con funciones de supervivencia de un sitio a un grupo de servidores o un servidor Standard Edition, el valor predeterminado es de 120 segundos para conmutación por error y 240 segundos para reserva.

### <a name="web-services"></a>Servicios web

Para editar o especificar opciones adicionales de los servicios web en el servidor, modifique o especifique los valores en los **servicios web internos** o **servicios web externos**.

Para **Servicios Web internos**, especifique lo siguiente:

- Si selecciona Invalidar nombre de dominio completo, puede especificar un nombre de dominio completo para la identidad de servicios web internos en el servidor. De forma predeterminada, la opción es el nombre actual del servidor que está definido en el servidor Standard Edition.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 80 para HTTP y puerto 443 para HTTPS son los más habituales; en general, no hace falta cambiarlos a menos que la organización o el diseño de la infraestructura presenten unos requisitos concretos.

Para **Servicios Web externos**, especifique lo siguiente:

- El FQDN de los servicios web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.

- Los puertos de escucha de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 8080 para HTTP y puerto 4443 para HTTPS se definen al principio. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Estos valores determinan los puertos que el servidor escuchará para solicitudes entrantes. En general no hace falta cambiarlos, a menos que en el servidor haya un conflicto de requisitos de puertos.

### <a name="mediation-server"></a>Servidor de mediación

Para **Servidor de mediación**, puede especificar lo siguiente:

- Si combina el servidor de mediación con el servidor, seleccione la casilla **Servidor de mediación combinado habilitado**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción disponible.

- Si ha habilitado la combinación del servidor de mediación, el intervalo de puertos de escucha del servidor debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la RTC para saber si realmente lo necesita. De forma predeterminada, el valor de este puerto es 5068.

- Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

- Si tiene asociada más de una puerta de enlace con un servidor de mediación, puede especificar un puerta de enlace como predeterminada. Para ello, haga clic en la puerta de enlace y, a continuación, haga clic en **Convertir en predeterminada**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.

Para obtener más información, sobre la definición y configuración de opciones para el servidor Standard Edition, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


