---
title: Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumen: Crear o modificar directivas de voz y configurar registros de uso de RTC mediante la Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 04cfca012490174bfefaa39c4456041ee294385c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965474"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa
 
**Resumen:** Crear o modificar directivas de voz y configurar registros de uso de RTC mediante la Skype para el Panel de Control de servidor empresarial.
  
> [!NOTE]
> Cada directiva de voz debe tener al menos un registro de uso de RTC asociado. Para ver una lista de todos los registros de uso de RTC disponibles en su implementación de Enterprise Voice y ver sus propiedades, vea [los registros de uso de RTC de vista en Skype para la empresa](view-pstn-usage-records.md). 
  
### <a name="to-create-a-voice-policy"></a>Para crear una directiva de voz

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y luego en **Directiva de voz**.
    
3. En la página **Directiva de voz**, haga clic en **Nueva** y seleccione el ámbito de la nueva directiva:
    
   - La **directiva de sitio** se aplica a todo un sitio, excepto a los usuarios o grupos que estén asignados a una directiva de usuario. Si selecciona Sitio al definir el ámbito de la directiva, elija un sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se creó una directiva de voz para un sitio, el sitio no aparecerá en el cuadro de diálogo **Seleccionar un sitio**.
    
   - La **directiva de usuario** se puede aplicar a usuarios o grupos concretos.
    
4. Si el ámbito de una directiva de voz es Usuario, escriba un nombre descriptivo para la directiva en el campo **Nombre**.
    
    > [!NOTE]
    > Si el ámbito de la directiva de voz es Sitio, el campo **Nombre** de **Nueva directiva de voz** se rellena automáticamente con el nombre del sitio y no se puede cambiar.
  
5. (Opcional) Agregue información descriptiva sobre la directiva de voz.
    
6. Active o desactive las siguientes casillas para habilitar o deshabilitar cada una de las **Características de llamada** de esta directiva de voz:
    
   - **Escape de correo de voz** evita que las llamadas se enrute inmediatamente al sistema de correo de voz de teléfono móvil del usuario cuando las llamadas simultáneas se configura y el teléfono está desactivado, fuera de la batería o fuera del intervalo.
    
    > [!NOTE]
    > Esta característica sólo es configurable a través de la Skype para Shell de administración de servidor empresarial 
  
   - **Desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype para Business Server proporciona una gama mucho más amplia de opciones de configuración de desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Esta opción está habilitada de forma predeterminada.
    
   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype para Business Server, un delegado puede configurar las llamadas simultáneas que permite que las llamadas entrantes a su jefe llamar a todos los destinos de llamadas simultáneas del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Esta opción está habilitada de forma predeterminada.
    
   - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.
    
   - El **estacionamiento de llamadas** permite a los usuarios poner llamadas en espera y después recibir la llamada de otro teléfono o cliente. Está opción está deshabilitada de forma predeterminada.
    
   - La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Skype para Business Server proporciona una gama mucho más amplia de opciones de configuración para las llamadas simultáneas. Está habilitada de forma predeterminada.
    
   - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.
    
   - **Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a redirigir en la RTC si la red WAN está saturada o no disponible. Está habilitada de forma predeterminada.
    
   - El **reemplazo de directiva de ancho de banda** permite a los administradores cambiar las decisiones de la directiva del servicio de control de admisión de llamadas para un usuario en concreto. Esta opción está deshabilitada de forma predeterminada.
    
    > [!NOTE]
    > La directiva se reemplazará solo para las llamadas entrantes que reciba el usuario, y no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación, y recomendamos evitarla para tomar las decisiones correctas en el control de admisión de llamadas. 
  
   - El **seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas) usando la interfaz de usuario del cliente, y hace que la llamada quede señalada en los registros de detalles de llamadas (CDR). Está deshabilitada de forma predeterminada.
    
   - **Opciones de disponibilidad** habilita o deshabilita las opciones de disponibilidad para la directiva de voz especificada. Permite que se enruten las llamadas entrantes al correo de voz o que se rechacen con una señal de ocupado cuando el usuario objetivo de la llamada está usando el teléfono. Opciones de disponibilidad constituye una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016. Si se activa este parámetro, se habilitan las opciones de disponibilidad, si se lo desactiva, se deshabilitan. Para obtener más información, consulte [Plan para las opciones de disponibilidad de Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) y [instalar y configurar las opciones de disponibilidad de Skype para Business Server](install-and-configure-busy-options.md).
    
7. Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:
    
   - Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.
    
   - Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.
    
   - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:
    
    a. Haga clic en **Nuevo**.
    
    b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, es posible que desee crear un namedRedmond de registro de uso de RTC para empleados de jornada completa que se encuentra en Redmond y otro namedRedmondTemps para los empleados temporales.
    
    > [!NOTE]
    > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.
  
    c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    d. Haga clic en **Aceptar**.
    
   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
    
    a. Resalte el registro de uso de RTC que desea editar y haga clic en **Mostrar detalles**.
    
    b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya está asociada a este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    c. Haga clic en **Aceptar**.
    
8. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre de registro y haga clic en arriba o flecha abajo.
    
    > [!IMPORTANT]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype para Business Server recorre la lista desde la parte superior hacia abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. 
  
9. Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:
    
   - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.
    
   - Para permitir que el desvío de llamadas y las llamadas simultáneas a Skype interna para los usuarios de negocios, seleccione la opción **ruta a Skype interna para los usuarios de negocios** en el menú desplegable. Las llamadas no se desviarán a los números de RTC externos.
    
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
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    d. Haga clic en **Aceptar**.
    
   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
    
    a. Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
    
    b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    c. Haga clic en **Aceptar**.
    
10. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.
    
11. Haga clic en **Aceptar**.
    
12. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**. 
    
    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, ejecute el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  
13. (Opcional) Correo de voz Escape detecta que una llamada se respondió inmediatamente por correo de voz de teléfono móvil del usuario y desconecta de la llamada al correo de voz de teléfono móvil. Esto permite la llamada pasar a llamar en el usuario de otros extremos dar al usuario la oportunidad de responder a la llamada. Para obtener información detallada acerca de cómo configurar una directiva de correo de voz, vea [Configure escape de correo de voz de Skype para la empresa](configure-voice-mail-escape.md).
    
### <a name="to-modify-a-voice-policy"></a>Para modificar una directiva de voz

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.
    
3. En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.
    
    > [!NOTE]
    > El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse. 
  
4. (Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.
    
5. Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:
    
   - **Escape de correo de voz** evita que las llamadas se enrute inmediatamente al sistema de correo de voz de teléfono móvil del usuario cuando las llamadas simultáneas se configura y el teléfono está desactivado, fuera de la batería o fuera del intervalo.
    
    > [!NOTE]
    > Esta característica sólo es configurable a través de la Skype para Shell de administración de servidor empresarial 
  
   - **Desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Skype para Business Server proporciona una gama mucho más amplia de opciones de configuración de desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Esta opción está habilitada de forma predeterminada.
    
   - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Skype para Business Server, un delegado puede configurar las llamadas simultáneas que permite que las llamadas entrantes a su jefe llamar a todos los destinos de llamadas simultáneas del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Esta opción está habilitada de forma predeterminada.
    
   - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.
    
   - El **estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Esta opción está deshabilitada de forma predeterminada.
    
   - La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Skype para Business Server proporciona una gama mucho más amplia de opciones de configuración para las llamadas simultáneas. Está habilitada de forma predeterminada.
    
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
    
    b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, es posible que desee crear un namedRedmond de registro de uso de RTC para empleados de jornada completa que se encuentra en Redmond y otro namedRedmondTemps de registro para los empleados temporales.
    
    > [!NOTE]
    > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.
  
    c. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
   - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    d. Haga clic en **Aceptar**.
    
   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
    
    a. Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.
    
    b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
   - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
   - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. 
    
    c. Haga clic en **Aceptar**.
    
7. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre de registro y haga clic en arriba o flecha abajo.
    
    > [!NOTE]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Skype para Business Server recorre la lista desde la parte superior hacia abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. 
  
8. Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:
    
   - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.
    
   - Para permitir que el desvío de llamadas y las llamadas simultáneas a Skype interna para los usuarios de negocios, seleccione **ruta de Skype interna para los usuarios de negocios** en el menú desplegable. Las llamadas no se desviarán a los números de RTC externos.
    
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
    
   - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
   - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener información detallada, vea [modificar una ruta de voz](http://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).
    
    d. Haga clic en **Aceptar**.
    
   - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
    
     a. Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.
    
     b. Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
     - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
    
     - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
    
     - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).
    
     - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener información detallada, vea [modificar una ruta de voz](http://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).
    
     c. Haga clic en **Aceptar**.
    
9. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.
    
10. Haga clic en **Aceptar**.
    
11. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**. 
    
    > [!NOTE]
    > Al crear o modifica runa directiva de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  
12. (Opcional) Correo de voz Escape detecta que una llamada se respondió inmediatamente por correo de voz de teléfono móvil del usuario y desconecta de la llamada al correo de voz de teléfono móvil. Esto permite la llamada pasar a llamar en el usuario de otros extremos dar al usuario la oportunidad de responder a la llamada. Para obtener información detallada sobre cómo configurar una directiva de correo de voz, vea [Configure escape de correo de voz de Skype para la empresa](configure-voice-mail-escape.md).
    
## <a name="see-also"></a>Vea también

[Ver registros de uso de RTC de Skype para la empresa](view-pstn-usage-records.md)
  
[Crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md)
  
[Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md)
  
[Configurar escape de correo de voz de Skype para la empresa](configure-voice-mail-escape.md)

