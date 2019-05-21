---
title: Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumen: cree o modifique directivas de voz y configure los registros de uso de RTC con el panel de control de Skype empresarial Server.'
ms.openlocfilehash: b9024ea1efac7f58fea7175f22f85b325ab5a43c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300897"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial

**Resumen:** Cree o modifique directivas de voz y configure los registros de uso de RTC con el panel de control de Skype empresarial Server.

> [!NOTE]
> Cada directiva de voz debe tener al menos un registro de uso de RTC asociado. Para ver una lista de todos los registros de uso de RTC disponibles en su implementación de telefonía IP empresarial y ver sus propiedades, consulte [ver los registros de uso de RTC en Skype empresarial](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Para crear una directiva de voz

1. Abra el panel de control de Skype empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y luego en **Directiva de voz**.

3. En la página **Directiva de voz**, haga clic en **Nueva** y seleccione el ámbito de la nueva directiva:

   - La **directiva de sitio** se aplica a todo un sitio, excepto a los usuarios o grupos que estén asignados a una directiva de usuario. Si selecciona Sitio al definir el ámbito de la directiva, elija un sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se creó una directiva de voz para un sitio, el sitio no aparecerá en el cuadro de diálogo **Seleccionar un sitio**.

   - La **directiva de usuario** se puede aplicar a usuarios o grupos concretos.

4. Si el ámbito de una directiva de voz es Usuario, escriba un nombre descriptivo para la directiva en el campo **Nombre**.

    > [!NOTE]
    > Si el ámbito de la directiva de voz es Sitio, el campo **Nombre** de **Nueva directiva de voz** se rellena automáticamente con el nombre del sitio y no se puede cambiar.

5. (Opcional) Agregue información descriptiva sobre la directiva de voz.

6. Active o desactive las siguientes casillas para habilitar o deshabilitar cada una de las **Características de llamada** de esta directiva de voz:

   - El **escape del correo de voz** impide que las llamadas se enruten inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se configura el timbre simultáneo y el teléfono está apagado, fuera de la batería o fuera del alcance.

     > [!NOTE]
     > Esta característica solo se puede configurar a través del shell de administración de Skype empresarial Server.

   - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype empresarial Server proporciona una variedad significativamente más amplia de opciones de configuración para el desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Está habilitado de forma predeterminada.

   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype empresarial Server, un delegado puede configurar la llamada simultánea que permite que las llamadas entrantes a su administrador suenen en todos los destinos de timbre simultáneo del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Esta opción está habilitada de forma predeterminada.

   - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.

   - El **estacionamiento de llamadas** permite a los usuarios poner llamadas en espera y después recibir la llamada de otro teléfono o cliente. Está opción está deshabilitada de forma predeterminada.

   - La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Skype empresarial Server proporciona una variedad significativamente más amplia de opciones de configuración para llamadas simultáneas. Está habilitado de forma predeterminada.

   - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.

   - **Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a redirigir en la RTC si la red WAN está saturada o no disponible. Está habilitada de forma predeterminada.

   - El **reemplazo de directiva de ancho de banda** permite a los administradores cambiar las decisiones de la directiva del servicio de control de admisión de llamadas para un usuario en concreto. Esta opción está deshabilitada de forma predeterminada.

     > [!NOTE]
     > La directiva se reemplazará solo para las llamadas entrantes que reciba el usuario, y no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación, y recomendamos evitarla para tomar las decisiones correctas en el control de admisión de llamadas.

   - El **seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas) usando la interfaz de usuario del cliente, y hace que la llamada quede señalada en los registros de detalles de llamadas (CDR). Está deshabilitada de forma predeterminada.

   - **Opciones de disponibilidad** habilita o deshabilita las opciones de disponibilidad para la directiva de voz especificada. Permite que se enruten las llamadas entrantes al correo de voz o que se rechacen con una señal de ocupado cuando el usuario objetivo de la llamada está usando el teléfono. Opciones de disponibilidad constituye una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016. Si se activa este parámetro, se habilitan las opciones de disponibilidad, si se lo desactiva, se deshabilitan. Para obtener más información, vea [planear las opciones de ocupado para Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) e [instalar y configurar opciones de disponibilidad para Skype empresarial Server](install-and-configure-busy-options.md).

7. Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:

   - Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, es posible que desee crear un registro de uso de RTC namedRedmond para empleados de tiempo completo ubicados en Redmond y otro namedRedmondTemps para empleados temporales.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:

     a. Resalte el registro de uso de RTC que desea editar y haga clic en **Mostrar detalles**.

     b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya está asociada a este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

8. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.

    > [!IMPORTANT]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype empresarial Server recorre la lista desde arriba hacia abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:

   - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.

   - Para permitir el desvío de llamadas y las llamadas simultáneas solo a usuarios internos de Skype empresarial, seleccione la opción enrutar solo **a los usuarios internos de Skype empresarial** en el menú desplegable. Calls will not be forwarded to external PSTN numbers.

   - Para usar unos registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas que no sean los que se usan para esta directiva de voz, seleccione la opción **Distribuir con los usos de la RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar registros de uso de RTC o crear nuevos registros de uso de RTC destinados concretamente a desviar llamadas o a realizar llamadas simultáneas.

   - Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y de llamadas simultáneas, resalte el registro y haga clic en **Quitar**.

   - Para definir un registro de uso de RTC nuevo y asociarlo a esta directiva de desvío de llamadas y de llamadas simultáneas, haga lo siguiente:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

     b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

10. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.

11. Haga clic en **Aceptar**.

12. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, ejecute el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.

13. Faculta El buzón de voz ESC detecta que la llamada fue respondida inmediatamente por el correo de voz del teléfono móvil del usuario y desconecta la llamada al correo de voz del teléfono móvil. Esto permite que la llamada continúe sonando en los otros puntos de conexión del usuario, lo que ofrece al usuario la oportunidad de contestar la llamada. Para obtener más información sobre cómo configurar una directiva de correo de voz, vea Configurar la configuración [de ESC de correo de voz en Skype empresarial](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Para modificar una directiva de voz

1. Abra el panel de control de Skype empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.

3. En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.

    > [!NOTE]
    > El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.

4. (Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.

5. Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:

   - El **escape del correo de voz** impide que las llamadas se enruten inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se configura el timbre simultáneo y el teléfono está apagado, fuera de la batería o fuera del alcance.

     > [!NOTE]
     > Esta característica solo se puede configurar a través del shell de administración de Skype empresarial Server.

   - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype empresarial Server proporciona una variedad significativamente más amplia de opciones de configuración para el desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Está habilitado de forma predeterminada.

   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype empresarial Server, un delegado puede configurar la llamada simultánea que permite que las llamadas entrantes a su administrador suenen en todos los destinos de timbre simultáneo del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Esta opción está habilitada de forma predeterminada.

   - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.

   - El **estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Esta opción está deshabilitada de forma predeterminada.

   - La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Skype empresarial Server proporciona una variedad significativamente más amplia de opciones de configuración para llamadas simultáneas. Está habilitada de forma predeterminada.

   - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.

   - **Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a redirigir en la RTC si la red WAN está saturada o no disponible. Está habilitada de forma predeterminada.

   - El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Está deshabilitada de forma predeterminada.

     > [!NOTE]
     > La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.

   - **Seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas de bomba) usando la interfaz de usuario del cliente, con lo cual la llamada queda señalada en los registros de detalles de llamadas. Está deshabilitada de forma predeterminada.

6. Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:

   - Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, es posible que desee crear un registro de uso de RTC namedRedmond para empleados de tiempo completo ubicados en Redmond y otro registro namedRedmondTemps para empleados temporales.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.

     b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

7. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.

    > [!NOTE]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype empresarial Server recorre la lista desde arriba hacia abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:

   - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.

   - Para permitir el desvío de llamadas y las llamadas simultáneas solo a usuarios internos de Skype empresarial, seleccione enrutar **a los usuarios internos de Skype empresarial solo** en el menú desplegable. Calls will not be forwarded to external PSTN numbers.

   - Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Distribuir con los usos de la RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.

   - Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y de llamadas simultáneas, resalte el registro y haga clic en **Quitar**.

   - Para definir un registro de uso de RTC nuevo y asociarlo a esta directiva de desvío de llamadas y de llamadas simultáneas, haga lo siguiente:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     d. Haga clic en **Aceptar**.

   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:

     a. Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.

     b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

     - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.

     - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.

     - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md).

     - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Haga clic en **Aceptar**.

9. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.

10. Haga clic en **Aceptar**.

11. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**.

    > [!NOTE]
    > Al crear o modifica runa directiva de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.

12. Faculta El buzón de voz ESC detecta que la llamada fue respondida inmediatamente por el correo de voz del teléfono móvil del usuario y desconecta la llamada al correo de voz del teléfono móvil. Esto permite que la llamada continúe sonando en los otros puntos de conexión del usuario, lo que ofrece al usuario la oportunidad de contestar la llamada. Para obtener más información sobre cómo configurar una directiva de correo de voz, vea Configurar la configuración [de ESC de correo de voz en Skype empresarial](configure-voice-mail-escape.md).

## <a name="see-also"></a>Vea también

[Ver los registros de uso de RTC en Skype empresarial](view-pstn-usage-records.md)

[Crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md)

[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype empresarial](voice-route-config-changes.md)

[Configurar el escape del correo de voz en Skype empresarial](configure-voice-mail-escape.md)

