---
title: Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumen: cree o modifique directivas de voz y configure los registros de uso de RTC mediante el Panel de control de Skype Empresarial Server.'
ms.openlocfilehash: 3e0fe5cebfc9d46f5c21554f1e18b54799d2d1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830410"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial

**Resumen:** Crear o modificar directivas de voz y configurar registros de uso de RTC mediante el Panel de control de Skype Empresarial Server.

> [!NOTE]
> Cada directiva de voz debe tener al menos un registro de uso de la red telefónica conmutada (RTC) asociado. Para ver una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial y ver sus propiedades, consulte Ver registros de uso de RTC [en Skype Empresarial.](view-pstn-usage-records.md)

### <a name="to-create-a-voice-policy"></a>Para crear una directiva de voz

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y luego en **Directiva de voz**.

3. En la página **Directiva de voz**, haga clic en **Nueva** y seleccione el ámbito de la nueva directiva:

   - La **directiva de sitio** se aplica a todo un sitio, excepto a los usuarios o grupos que estén asignados a una directiva de usuario. Si selecciona Sitio al definir el ámbito de la directiva, elija un sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se creó una directiva de voz para un sitio, el sitio no aparecerá en el cuadro de diálogo **Seleccionar un sitio**.

   - La **directiva de usuario** se puede aplicar a usuarios o grupos concretos.

4. Si el ámbito de una directiva de voz es Usuario, escriba un nombre descriptivo para la directiva en el campo **Nombre**.

    > [!NOTE]
    > Si el ámbito de la directiva de voz es Sitio, el campo **Nombre** de la **Nueva directiva de voz** se rellena automáticamente con el nombre del sitio y no se puede cambiar.

5. (Opcional) Añada información descriptiva sobre la directiva de voz.

6. Active o desactive las siguientes casillas para habilitar o deshabilitar cada una de las **Características de llamada** de esta directiva de voz:

   - **El** escape de correo de voz impide que las llamadas se enrutan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se configuran las llamadas simultáneas y el teléfono está apagado, sin batería o fuera del alcance.

     > [!NOTE]
     > Esta característica solo se puede configurar a través del Shell de administración de Skype Empresarial Server

   - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype Empresarial Server ofrece una amplia gama de opciones de configuración para el reenvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la Red telefónica conmutada (RTC), un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Habilitada de forma predeterminada.

   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype Empresarial Server, un delegado puede configurar llamadas simultáneas que permiten que las llamadas entrantes a su administrador suene todos los destinos de llamadas simultáneas del delegado. Así pues, el delegado dispone de una mayor flexibilidad para responder a las llamadas dirigidas a su superior. Habilitada de forma predeterminada.

   - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Opción habilitada habitualmente.

   - El **estacionamiento de llamadas** permite a los usuarios poner llamadas en espera y después recibir la llamada de otro teléfono o cliente. Opción deshabilitada habitualmente.

   - **Llamadas simultáneas** permite que las llamadas entrantes suenen en otros teléfonos (por ejemplo, un teléfono móvil) o en otros dispositivos de extremo. Skype Empresarial Server ofrece una gama mucho más amplia de opciones de configuración para las llamadas simultáneas. Habilitada de forma predeterminada.

   - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Habilitada de forma predeterminada.

   - **La** reenrutamiento de RTC permite que las llamadas realizadas por los usuarios que tienen asignada esta directiva a otros usuarios de la empresa se desvíen en la RTC si la RED WAN está congestionada o no disponible. Habilitado de forma predeterminada.

   - El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Opción deshabilitada habitualmente.

     > [!NOTE]
     > La directiva se reemplazará solo para las llamadas entrantes que reciba el usuario, y no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación, y recomendamos evitarla para tomar las decisiones correctas en el control de admisión de llamadas.

   - **El seguimiento de** llamadas malintencionadas permite a los usuarios notificar llamadas malintencionadas (como amenazas) mediante la interfaz de usuario del cliente, que a su vez marca las llamadas en los registros de detalles de llamadas (CDR). Deshabilitado de forma predeterminada.

   - **Las opciones de** disponibilidad habilitan o deshabilitan Opciones de disponibilidad para la directiva de voz especificada. Opciones de disponibilidad permite que las llamadas entrantes se enrutar al correo de voz o que se rechacen con una señal de ocupado cuando el usuario de destino de la llamada está en el teléfono. Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016. Si se activa este parámetro, se habilitan opciones de disponibilidad y, si se desactiva, se deshabilitan las opciones de disponibilidad. Para obtener más información, consulte [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and Install and configure Busy Options for Skype for Business [Server](install-and-configure-busy-options.md).

7. Para asociar y configurar registros de uso de RTC para esta directiva de voz, siga uno de los procedimientos siguientes:

   - Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y haga clic en **Aceptar**.

   - Para quitar el registro de uso de RTC de esta directiva de voz, seleccione el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo con esta directiva de voz, haga lo siguiente:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, es posible que desee crear un registro de uso de RTC denominadoRedmond para empleados a tiempo completo ubicados en Redmond y otro llamadoRedmondTemps para empleados temporales.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:

     a. Resalte el registro de uso de RTC que desea editar y haga clic en **Mostrar detalles**.

     b. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya está asociado a este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

8. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.

    > [!IMPORTANT]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype Empresarial Server recorre la lista de arriba abajo. Se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Para asociar y configurar los registros de uso de RTC correspondientes al desvío de llamadas y a las llamadas simultáneas de esta directiva de voz, realice una de las siguientes acciones:

   - Para usar los mismos registros de uso de RTC en el desvío de llamadas y las llamadas simultáneas que esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC de llamada** en el menú desplegable.

   - Para permitir el reenvío de llamadas y las llamadas simultáneas solo a usuarios internos de Skype Empresarial, seleccione la opción Ruta a usuarios internos de **Skype** Empresarial solo en el menú desplegable. Las llamadas no se desviarán a los números de RTC externos.

   - Para usar unos registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas que no sean los que se usan para esta directiva de voz, seleccione la opción **Redirigir con usos de PSTN personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar registros de uso de RTC o crear nuevos registros de uso de RTC destinados concretamente a desviar llamadas o a realizar llamadas simultáneas.

   - Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y llamadas simultáneas, resalte el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de desvío de llamadas y llamadas simultáneas:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

     b. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

10. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.

11. Haga clic en **Aceptar**.

12. En la página **Directiva de voz**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, ejecute el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

13. (Opcional) Voicemail Escape detecta que el correo de voz del teléfono móvil del usuario ha respondido inmediatamente a una llamada y desconecta la llamada al correo de voz del teléfono móvil. Esto permite que la llamada siga sonando en los otros puntos de conexión del usuario, lo que da al usuario la oportunidad de responder a la llamada. Para obtener más información sobre cómo configurar una directiva de correo de voz, consulte Configurar el escape de correo de [voz en Skype Empresarial.](configure-voice-mail-escape.md)

### <a name="to-modify-a-voice-policy"></a>Para modificar una directiva de voz

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.

3. En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.

    > [!NOTE]
    > El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.

4. (Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.

5. Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:

   - **El** escape de correo de voz impide que las llamadas se enrutan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se configuran las llamadas simultáneas y el teléfono está apagado, sin batería o fuera del alcance.

     > [!NOTE]
     > Esta característica solo se puede configurar a través del Shell de administración de Skype Empresarial Server

   - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype Empresarial Server ofrece una amplia gama de opciones de configuración para el reenvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la Red telefónica conmutada (RTC), un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Habilitada de forma predeterminada.

   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype Empresarial Server, un delegado puede configurar llamadas simultáneas que permiten que las llamadas entrantes a su administrador suene todos los destinos de llamadas simultáneas del delegado. Así pues, el delegado dispone de una mayor flexibilidad para responder a las llamadas dirigidas a su superior. Habilitada de forma predeterminada.

   - **Transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Habilitada de forma predeterminada.

   - **Estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Deshabilitada de forma predeterminada.

   - **Llamadas simultáneas** permite que las llamadas entrantes suenen en otros teléfonos (por ejemplo, un teléfono móvil) o en otros dispositivos de extremo. Skype Empresarial Server ofrece una gama mucho más amplia de opciones de configuración para las llamadas simultáneas. Habilitada de forma predeterminada.

   - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Habilitada de forma predeterminada.

   - **La** reenrutamiento de RTC permite que las llamadas realizadas por los usuarios que tienen asignada esta directiva a otros usuarios de la empresa se desvíen en la RTC si la RED WAN está congestionada o no disponible. Habilitado de forma predeterminada.

   - **La invalidación de la directiva** de ancho de banda permite a los administradores invalidar las decisiones de directiva de CAC para un usuario determinado. Deshabilitada de forma predeterminada.

     > [!NOTE]
     > La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.

   - **El seguimiento de llamadas** malintencionadas permite a los usuarios notificar llamadas malintencionadas (como amenazas) mediante la interfaz de usuario del cliente, que a su vez marca las llamadas en los CDR. Deshabilitada de forma predeterminada.

6. Para asociar y configurar registros de uso de RTC para esta directiva de voz, siga uno de los procedimientos siguientes:

   - Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y haga clic en **Aceptar**.

   - Para quitar el registro de uso de RTC de esta directiva de voz, seleccione el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo con esta directiva de voz, haga lo siguiente:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede crear un registro de uso de RTC denominadoRedmond para empleados a tiempo completo ubicados en Redmond y otro registro denominadoRedmondTemps para empleados temporales.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

     b. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

7. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.

    > [!NOTE]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype Empresarial Server recorre la lista de arriba abajo. Se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Para asociar y configurar los registros de uso de RTC correspondientes al desvío de llamadas y a las llamadas simultáneas de esta directiva de voz, realice una de las siguientes acciones:

   - Para usar los mismos registros de uso de RTC en el desvío de llamadas y las llamadas simultáneas que esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC de llamada** en el menú desplegable.

   - To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu. Las llamadas no se desviarán a números de RTC externos.

   - Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.

   - Para elegir uno o más registros de una lista con los registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desea asociar con esta directiva de desvío de voz y llamadas simultáneas y, después, haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y llamadas simultáneas, resalte el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de desvío de llamadas y llamadas simultáneas:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

     b. Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

     - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Enterprise Voice, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.

     - Para quitar una ruta de este registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.

     - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

     - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Haga clic en **Aceptar**.

9. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.

10. Haga clic en **Aceptar**.

11. En la página **Directiva de voz**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio en la configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

12. (Opcional) Voicemail Escape detecta que el correo de voz del teléfono móvil del usuario ha respondido inmediatamente a una llamada y desconecta la llamada al correo de voz del teléfono móvil. Esto permite que la llamada siga sonando en los otros puntos de conexión del usuario, lo que da al usuario la oportunidad de responder a la llamada. Para obtener más información sobre cómo configurar una directiva de correo de voz, consulte Configurar el escape de correo de [voz en Skype Empresarial.](configure-voice-mail-escape.md)

## <a name="see-also"></a>Vea también

[Ver registros de uso de RTC en Skype Empresarial](view-pstn-usage-records.md)

[Crear o modificar una ruta de voz en Skype Empresarial](create-or-modify-a-voice-route.md)

[Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial](voice-route-config-changes.md)

[Configurar el escape de correo de voz en Skype Empresarial](configure-voice-mail-escape.md)

