---
title: Expansor de configuración general front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 'Dispone de las siguientes secciones para editar la configuración de un grupo de servidores front-end o un servidor Standard Edition:'
ms.openlocfilehash: 1b28f3921042bcd8d0f8f99cd0b5950c190ef79d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201768"
---
# <a name="front-end-general-settings-expander"></a>Expansor de configuración general front-end

Dispone de las siguientes secciones para editar la configuración de un grupo de servidores front-end o un servidor Standard Edition:

- Configuración general

- Configuración de resistencia

- Configuración de servicios web

- Configuración del servidor de mediación

## <a name="front-end-pool"></a>Grupo de servidores front-end

En el caso de un grupo de servidores front-end, puede configurar las opciones generales, de resistencia, de servicios web y de servidor de mediación. Para más información, mire las subsecciones siguientes. Para más información sobre cómo definir y configurar opciones del grupo de servidores front-end, mire [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Configuración general

Puede definir la siguiente configuración general:

- **FQDN**. Edite el nombre de dominio completo del grupo de servidores para cambiarlo.

- **Habilitar el puerto de supervisión del equilibrador de carga de hardware**. Active la casilla e indique el número de puerto que el equilibrador de carga de hardware va a usar para supervisar el estado de los servidores del grupo de servidores.

- En **Características y funcionalidad**, defina los roles adicionales que quiera combinar con este grupo de servidores. Puede configurar lo siguiente:

  - **Conferencia**. Incluye las conferencias de audio, de vídeo y de uso compartido de aplicaciones. Tras seleccionar esta opción, puede elegir la conferencia de acceso telefónico local (RTC). Más avanzada esta sección, concretamente en la subsección “Configuración del servidor de mediación”, puede especificar y definir una puerta de enlace RTC.

  - **Telefonía IP empresarial**. Habilita voz interno a través de llamadas IP a los auriculares completo y dispositivos y Skype para clientes empresariales. Para habilitar las funciones de llamada externa, es necesario especificar un servidor de mediación. Para más información, mire “Servidor de mediación” más adelante en este tema.

- En **Asociaciones**, edite o especifique lo siguiente:

  - **Almacén de SQL**. Modifique una base de datos de SQL Server existente o cree una base de datos basada en SQL Server que hospede las bases de datos de grupos de servidores front-end. Puede seleccionar una nueva instancia de SQL Server de la lista o crear una entrada haciendo clic en **Nuevo**.

    Seleccione **Habilitar creación de reflejos del almacén de SQL Server** y, luego, seleccione el servidor que se va a usar para la creación de reflejos. Haga clic en **Nuevo** para crear un almacén de SQL Server.

    Seleccione **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática** para seleccionar un servidor y usarlo como testigo de creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server.

  - **Recurso compartido de archivos**. Modifique el almacén de archivos usado por el grupo de servidores front-end. Puede seleccionar un nuevo almacén de entre los que ya estén definidos en la lista o, también, crear un almacén de archivos haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.

  - **Archivado**. Asocie un almacén de servidor de archivado con el grupo de servidores front-end. Puede seleccionar un almacén de SQL Server de archivado de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor de archivado haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.

    Seleccione **Habilitar creación de reflejos del almacén de SQL Server** y, luego, seleccione el servidor que se va a usar para la creación de reflejos. Haga clic en **Nuevo** para crear un almacén de SQL Server.

    Seleccione **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática** para seleccionar un servidor y usarlo como testigo de creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server.

  - **Supervisión (métricas CDR y QoE)**. Seleccione esta opción para asociar un almacén de SQL Server de supervisión con el grupo de servidores front-end. Puede seleccionar un servidor de supervisión de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor de supervisión haciendo clic en **Nuevo**.

    Seleccione **Habilitar creación de reflejos del almacén de SQL Server** y, luego, seleccione el servidor que se va a usar para la creación de reflejos. Haga clic en **Nuevo** para crear un almacén de SQL Server.

    Seleccione **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática** para seleccionar un servidor y usarlo como testigo de creación de reflejo. Haga clic en **Nuevo** para crear un almacén de SQL Server.

  - **Asociar grupo de servidores perimetrales (para componentes multimedia)**. Asocie un servidor perimetral o un grupo de servidores perimetrales con el grupo de servidores front-end. Puede seleccionar un servidor perimetral o un grupo de servidores perimetrales de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor perimetral o grupo de servidores perimetrales haciendo clic en **Nuevo**.

  - **Asociar un grupo con un servidor de Office Web Apps**. Seleccione esta opción para asociar un servidor de Office Web Apps con el grupo de servidores front-end. Seleccione un servidor existente en la lista o haga clic en **Nuevo** para crear un servidor de Office Web Apps.

### <a name="resiliency"></a>Resistencia

La opción Resistencia proporciona funciones de recuperación ante desastres y alta disponibilidad al grupo de servidores. Al contar con una copia de seguridad, cuando se produzca un error en el servidor principal, se podrá recurrir al de copia de seguridad para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen en el servidor principal, los usuarios pueden llegar a tener un uso restringido de las funciones.

En la lista, seleccione el grupo de servidores front-end o el servidor Standard Edition que funcionará como servidor de copia de seguridad del grupo de servidores. También puede definir los intervalos de tiempo de conmutación por error y de reserva. Establecer un tiempo de conmutación por error y de reserva (en segundos) permite detectar automáticamente un servidor defectuoso; asimismo, el tiempo de reserva permite determinar automáticamente que el servidor principal tiene una copia de seguridad.

> [!IMPORTANT]
> Al definir el intervalo de detección de errores y de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva cuando se produzca un error en el servidor durante un período de tiempo breve. Es posible que el servidor principal no responda durante breves períodos, según la carga de los servidores o el grupo de servidores. Los valores predeterminados de conmutación por error y de reserva son de 300 segundos y 600 segundos de grupo de servidores a grupo de servidores, o de grupo de servidores a servidor Standard Edition. En el caso de una aplicación o servidor de sucursal con funciones de supervivencia de un sitio a un grupo de servidores o un servidor Standard Edition, el valor predeterminado es de 120 segundos para la conmutación por error y de 240 segundos para la reserva.

> [!CAUTION]
> No es aconsejable que el valor mínimo del **intervalo de conmutación por error** se encuentre por debajo de los 90 segundos. Cuando se define un valor inferior a 90 segundos, se usa el valor de 90 segundos. El tiempo de ping entre clústeres es de 30 segundos y, cuando se establece en menos de 90, puede dar como resultado un problema en el que los servidores principales y de copia de seguridad comienzan un ciclo ascendente y descendente, lo que afecta a la producción a medida que los servidores intentan resolver el estado viable del otro. Son necesarios al menos 90 segundos para determinar si el servidor principal realmente está disponible.

### <a name="web-services"></a>Servicios web

Para modificar o especificar más opciones de los servicios web en el grupo de servidores front-end, modifique o especifique las opciones que quiera en **Servicios web internos** y **Servicios web externos**.

Indique lo siguiente en **Servicios web internos**:

> [!CAUTION]
> Si tiene más de un grupo de servidores Front-End o servidor Front-End, los servicios Web externos FQDN debe ser único. Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores Front-End o servidor Front-End. Si también va a implementar los directores, el FQDN de servicios Web externos definidos para cualquier Director o grupo de directores debe ser único en cualquier otro Director o Director de grupo de servidores, como también a partir de cualquier Front-End del grupo de servidores o servidor Front-End. Si decide reemplazar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores Front-End, Director o Director de grupo de servidores.

- Si selecciona **FQDN de reemplazo**, puede especificar un nombre de dominio completo distinto para la identidad de **Servicios web internos** en el grupo de servidores. La configuración predeterminada es el nombre del grupo de servidores actual, según se haya definido para el grupo de servidores front-end.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 80 para HTTP y puerto 443 para HTTPS son los más habituales y, por lo general, no hace falta cambiarlos, a menos que la organización o el diseño de la infraestructura presenten unos requisitos concretos.

Indique lo siguiente en **Servicios web externos**:

- El FQDN de Servicios web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Se establecen los puertos publicados en valor predeterminado de puerto 80 para HTTP y el puerto 443 para HTTPS. Estos valores determinan qué puertos escuchará el grupo de servidores para las solicitudes entrantes. Normalmente, estos no es necesario que debe cambiar, a menos que haya un conflicto de los requisitos de puerto en el grupo de servidores. Se esperan internos y externos puertos publicados con los mismos valores de puerto. No es un conflicto.

### <a name="mediation-server"></a>Servidor de mediación

Puede especificar lo siguiente en relación con un **servidor de mediación**:

- Si está combinando el servidor de mediación con el grupo de servidores, active la casilla **Servidor de mediación combinado habilitado**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.

- Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor en los servidores del grupo para la Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.

- Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

- Si tiene asociado más de un tronco con un servidor de mediación, puede especificar uno de ellos como el tronco predeterminado. Para ello, seleccione la puerta de enlace y, luego, haga clic en **Establecer como predeterminado**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.

Para más información sobre cómo definir y configurar las opciones del grupo de servidores front-end, mire [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Servidor Standard Edition

En el caso de un servidor Standard Edition, puede configurar las opciones generales, de resistencia, de servicios web y de servidor de mediación. Para más información, mire las siguientes subsecciones. Para más información sobre cómo definir y configurar las opciones del servidor Standard Edition, mire [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Configuración general

Puede definir la siguiente configuración general:

- **FQDN**. El valor del nombre de dominio completo no se puede modificar. Para cambiar el nombre de dominio completo asociado con un servidor Standard Edition, necesita quitar y redefinir dicho servidor.

- Seleccione **Usar todas las direcciones IP configuradas** o **Limitar el uso del servicio a las direcciones IP seleccionadas**. Si decide limitar el servicio a determinadas direcciones IP definidas, necesitará definir la dirección IP principal que el servidor usará para todas las comunicaciones, excepto RTC. Para RTC hay que definir una dirección IP aparte. También puede seleccionar **Habilitar IPv6** para habilitar IPv6 para este servidor.

- **Habilitar el puerto de supervisión del equilibrador de carga de hardware**. Active la casilla e indique el número de puerto que el equilibrador de carga de hardware va a usar para supervisar el estado del servidor.

- En **Características y funcionalidad**, defina los roles extra que quiera combinar con este servidor. Puede configurar lo siguiente:

  - **Conferencia**. Incluye las conferencias de audio, de vídeo y de uso compartido de aplicaciones. Tras seleccionar esta opción, puede elegir **Conferencia de acceso telefónico local (RTC)**. Más adelante, concretamente en la sección de configuración del servidor de mediación, puede especificar y definir una puerta de enlace RTC.

  - **Telefonía IP empresarial**. Habilita voz interno a través de llamadas IP a los auriculares completo y dispositivos y Skype para clientes empresariales. Para habilitar las funciones de llamada externa, es necesario especificar un servidor de mediación. Para más información, mire “Servidor de mediación” más adelante en este tema.

- En **Asociaciones**, puede editar o especificar lo siguiente:

  - Seleccione **Almacén de SQL Server** para asociar un almacén de SQL Server con el servidor front-end. También puede habilitar la creación de reflejos y seleccionar un servidor testigo de creación de reflejos.

  - **Recurso compartido de archivos**. Modifique el almacén de archivos usado por el servidor Standard Edition. Puede seleccionar un nuevo almacén de entre los que ya estén definidos en la lista o, también, crear un almacén de archivos haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.

  - **Archivado**. Asocie un almacén de servidor de archivado con el servidor Standard Edition. Puede seleccionar un almacén de SQL Server de archivado de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor de archivado haciendo clic en **Nuevo**.

    > [!IMPORTANT]
    > Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.

  - **Supervisión (métricas CDR y QoE)**. Asocie un almacén de SQL Server de supervisión con el servidor Standard Edition. Puede seleccionar un servidor de supervisión de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor de supervisión haciendo clic en **Nuevo**.

  - **Asociar un grupo con un servidor de Office Web Apps**. Seleccione esta opción para asociar un servidor de Office Web Apps con el grupo de servidores front-end. Seleccione un servidor existente en la lista o haga clic en **Nuevo** para crear un servidor de Office Web Apps.

  - **Asociar grupo de servidores perimetrales**. Asocie un servidor perimetral o un grupo de servidores perimetrales con el servidor Standard Edition. Puede seleccionar un servidor perimetral o un grupo de servidores perimetrales de entre los que ya estén definidos en la lista o, también, especificar un nuevo servidor perimetral o grupo de servidores perimetrales haciendo clic en **Nuevo**.

### <a name="resiliency"></a>Resistencia

La opción Resistencia proporciona funciones de recuperación ante desastres y alta disponibilidad al servidor. Al contar con una copia de seguridad, cuando se produzca un error en el servidor principal, se podrá recurrir al de copia de seguridad para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen en el servidor principal, los usuarios pueden llegar a tener un uso restringido de las funciones.

En la lista, seleccione el grupo de servidores front-end o el servidor Standard Edition que funcionará como servidor de copia de seguridad del servidor. También puede definir los intervalos de tiempo de conmutación por error y de reserva. Configurar un tiempo de conmutación por error y de reserva (en segundos) permite detectar automáticamente un registrador defectuoso; asimismo, el tiempo de reserva permite determinar automáticamente que el servidor principal tiene una copia de seguridad.

> [!IMPORTANT]
> Al definir el intervalo de detección de errores y de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva cuando se produzca un error en el servidor durante un período de tiempo breve. Es posible que el servidor principal no responda durante breves períodos, según la carga de los servidores o el grupo de servidores. Los valores predeterminados de conmutación por error y de reserva son de 300 segundos y 600 segundos de grupo de servidores a grupo de servidores, o de grupo de servidores a servidor Standard Edition. En el caso de una aplicación o servidor de sucursal con funciones de supervivencia de un sitio a un grupo de servidores o un servidor Standard Edition, el valor predeterminado es de 120 segundos para la conmutación por error y de 240 segundos para la reserva.

### <a name="web-services"></a>Servicios web

Para modificar o especificar más opciones de los servicios web en el servidor, modifique o especifique las opciones que quiera en **Servicios web internos** y **Servicios web externos**.

Indique lo siguiente en **Servicios web internos**:

- Si selecciona FQDN de reemplazo, puede especificar un nombre de dominio completo distinto para la identidad de Servicios web internos en el servidor. La configuración predeterminada es el nombre de servidor actual, según se haya definido para servidor Standard Edition.

- Los puertos de escucha y publicados de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 80 para HTTP y puerto 443 para HTTPS son los más habituales y, por lo general, no hace falta cambiarlos, a menos que la organización o el diseño de la infraestructura presenten unos requisitos concretos.

Indique lo siguiente en **Servicios web externos**:

- El FQDN de Servicios web externos. El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.

- Los puertos de escucha de HTTP y HTTPS que la implementación necesita. Los valores predeterminados de puerto 8080 para HTTP y puerto 4443 para HTTPS se definen al principio. Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa. Estos valores determinan los puertos que el servidor escuchará para solicitudes entrantes. En general, no hace falta cambiarlos, a menos que haya un conflicto de requisitos de puertos en el servidor.

### <a name="mediation-server"></a>Servidor de mediación

Puede especificar lo siguiente en relación con un **servidor de mediación**:

- Si está combinando el servidor de mediación con el servidor, active la casilla **Servidor de mediación combinado habilitado**. Si opta por no combinar el servidor de mediación, en esta sección no hay ninguna opción que se deba configurar.

- Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor para TLS. Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesitará definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.

- Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

- Si tiene asociada más de una puerta de enlace con un servidor de mediación, puede especificar una de ellas como la puerta de enlace predeterminada. Para ello, seleccione la puerta de enlace y, luego, haga clic en **Establecer como predeterminado**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.

Para más información sobre cómo definir y configurar las opciones del servidor Standard Edition, mire [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


