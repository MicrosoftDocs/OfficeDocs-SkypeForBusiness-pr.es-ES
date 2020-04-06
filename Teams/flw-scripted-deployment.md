---
title: Aprovisionamiento de Microsoft Teams en escala para los Firstline Workers
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Guía sobre el uso de scripts para implementar o aprovisionar Microsoft Teams a los Firstline Workers.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: caecd0d97e760470604fa164e6356a59699e57ad
ms.sourcegitcommit: bc1d2e0478a429f981b53765e6194443b32ae35c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43122924"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>Cómo proporcionar Teams a escala para Firstline Workers

¿Necesita incorporar rápidamente un gran número de usuarios a Microsoft Teams y configurar una experiencia optimizada para ellos? Puede aprovisionar rápidamente identidades, aprovisionar equipos y asignar todas las directivas relevantes para controlar la experiencia de usuario final siguiendo las siguientes instrucciones.

En este tutorial, aprenderá cómo hacerlo:

- Cree un gran número de usuarios.
- Cree un gran número de equipos y configure los canales adecuados.
- Asignar licencias a escala.
- Cree directivas de mensajería, directivas de configuración de aplicaciones y directivas de permisos de aplicación apropiados.
- Aplique estas directivas a los usuarios en escala.
- Asigne un gran número de usuarios a un equipo designado.

## <a name="prerequisites"></a>Requisitos previos

Descargue los recursos desde [esta ubicación](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).

> [!IMPORTANT]
> Los scripts que se incluyen en el vínculo presentado anteriormente se proporcionan en Microsoft y deben modificarse para sus necesidades individuales.

## <a name="technical-requirements"></a>Requisitos técnicos

- Su inquilino debe tener disponible el número de licencias apropiado, incluyendo Microsoft Teams. Si aún no tiene estas licencias, siga las instrucciones que se indican aquí para activar la [Prueba gratuita de Office 365 E1](e1-trial-license.md).
- El usuario que efectúe estos pasos debe hacerlo en el rol de administrador global o de administrador de usuarios en Azure AD.
- El usuario debe tener los permisos para instalar y configurar el software en su equipo local.

## <a name="step-by-step-process-overview"></a>Información general del proceso paso a paso

1. **Configure su entorno**
    1. Descargue el archivo ZIP que contiene los scripts de muestra de PowerShell y la documentación
    1. Configure las credenciales
    1. Configure el entorno local
    1. Configure los módulos de PowerShell y las variables de entorno
    1. Cree el registro de la aplicación
1. **Crear y configurar Teams**
    1. Cree Teams
    1. Cree canales para Teams
1. **Crear directivas de Teams**
    1. Cree directivas de mensajería de Teams
    1. Cree directivas de configuración de la aplicación Teams
    1. Cree directivas de permisos de aplicación de Teams
1. **Crear y configurar los usuarios**
    1. Cree usuarios y grupos de seguridad
    1. Asigne licencias a los usuarios a través de las licencias basadas en grupos
1. **Asignar usuarios y directivas**
    1. Asigne usuarios a Teams
    1. Asigne directivas a usuarios y grupos
1. **Probar y validar**
    1. Compruebe errores
    1. Inicie sesión en Teams con un usuario de prueba

## <a name="set-up-your-environment"></a>Configure su entorno

Los siguientes pasos le permitirán configurar su entorno:

### <a name="download-zip-file-containing-sample-powershell-scripts"></a>Descargue el archivo .zip que contiene los scripts de muestra de PowerShell

Para poder continuar, necesitará descargar los scripts en [esta ubicación](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).

### <a name="setup-credentials"></a>Configure las credenciales

En este documento y en los scripts de muestra hemos elegido crear un archivo de referencia que contiene sus credenciales para facilitar las cosas. Esta técnica elimina la necesidad de autenticarse en los diversos puntos de conexión del servicio, manteniendo al mismo tiempo las credenciales en un almacén local. Para poder ejecutar los scripts subsiguientes, deberá actualizar ese archivo de referencia con las credenciales que son únicas para usted y su entorno. A partir de cada script subsiguiente, las credenciales adecuadas se leen con la función auxiliar denominada **GetCreds** y estas credenciales se usan para conectarse a los distintos servicios.

No es raro que diferentes servicios requieran diferentes credenciales. Por ejemplo, puede tener diferentes credenciales para MicrosoftTeams, AzureAD y MSonline, en cuyo caso puede ejecutar SetCred guardando cada archivo de credenciales con su propio nombre significativo.

Ejemplos: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml

> [!NOTE]
> La cuenta usada para las credenciales no puede requerir MFA.

Este es un ejemplo de cómo los distintos scripts usan las credenciales guardadas para autenticarse:

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

Para configurar sus credenciales, haga lo siguiente:

1. Busque **SetCreds.ps1** en los recursos del archivo .zip.
1. Desde PowerShell, ejecute el script **SetCreds.ps1** para guardar sus credenciales.
    1. Se le pedirá que ejecute "realizar la operación" Export-Clixml "..." y tendrá que especificar "Y" para aprobar.

### <a name="configure-the-local-environment"></a>Configure el entorno local

1. Busque **SetConfig.ps1** en los recursos del archivo .zip.
1. Desde PowerShell, ejecute el siguiente comando y reemplace las entradas escalonadas con su información específica.
    1. **SetConfig.ps1** -tenantName [su nombre de inquilino] -rootPath "[ruta de acceso completa a la raíz del repositorio GIT]"

Por ejemplo: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`

### <a name="configure-powershell-modules-and-environmental-variables"></a>Configure los módulos de PowerShell y las variables de entorno

Antes de ir más allá, tendrá que instalar y conectarse a varios módulos de PowerShell, como Azure AD, MSAL, MSCloudUtils y MicrosoftTeams.

1. Busque **ConfigurePowerShellModules.ps1** en los recursos del archivo .zip.
1. Edite y reemplace las siguientes variables de entorno con sus variables:
1. Desde PowerShell, ejecute el script **ConfigurePowerShellModules.ps1**.

## <a name="create-and-set-up-teams"></a>Crear y configurar Teams

Para poder comunicarse y colaborar con sus Firstline Workers, primero tendrá que establecer una serie de Teams y agregar canales estándar a estos equipos, los cuales revisaremos a continuación.

### <a name="create-teams"></a>Crear equipos

Los equipos son un conjunto de personas, contenido y herramientas de su organización. Para la mayoría de las organizaciones centradas en Firstline Workers, se recomienda fijar un equipo en torno a una ubicación física. Por ejemplo, un equipo para cada uno de los siguientes:

- Almacén
- Centro de distribución
- Planta de fabricación
- Hospital
- Tienda de comestibles

*Discusión de prácticas recomendadas*: al designar equipos, es importante tener en cuenta los [límites de Teams y especificaciones](limits-specifications-teams.md). Para las organizaciones más pequeñas, un equipo para toda la organización se puede usar para simplificar la comunicación y complementar la estructura de una ubicación física. Para otras, una convención de nomenclatura de los grupos de ubicación física estructurada ayuda a las comunicaciones de la empresa con la publicación cruzada a múltiples equipos de forma simultánea con facilidad. Por ejemplo, puede buscar y cruzar a todos los equipos con EE. UU. en el nombre para señalar todas las ubicaciones de EE. UU. Puede encontrar más información sobre la publicación cruzada [aquí](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).

#### <a name="steps-to-create-teams"></a>Pasos para crear un equipo

1. Busque el archivo **Teams Information.csv** en los recursos.
1. Actualice la información en el archivo **Teams Information.csv** con la información específica de su organización. Tenga en cuenta las recomendaciones anteriores.
1. Busque el script **CreateTeams.ps1**
1. Desde PowerShell, ejecute el script **CreateTeams.ps1**

### <a name="create-channels-for-teams"></a>Cree canales para los equipos

Los canales son secciones dedicadas dentro de un equipo para mantener las conversaciones organizadas por temas, disciplinas o proyectos específicos. Cada equipo obtiene automáticamente un canal general, pero, desde allí, puede personalizar su estructura en función de las necesidades de su empresa. Por ejemplo, su estructura de canal adicional podría incluir:

- **Fabricación**: seguridad, línea 1, línea 2, comunicaciones corporativas, formación
- **Comestible**: panadería, producción, carne, comunicaciones corporativas, formación
- **Atención médica**: enfermeras, médicos, unidad de cuidados críticos 1, unidad de cuidados críticos 2
- **Hospitalidad**: recepción, mantenimiento, limpieza, valet y equipaje, comunicaciones corporativas, formación
- **Venta al por menor**: frente del almacén, detrás del almacén, comunicaciones corporativas, formación

> [!NOTE]
> Los canales no deben considerarse como un límite de seguridad. Son un medio de organizar a sus trabajadores con fines de colaboración.

*Discusión de prácticas recomendadas*: al diseñar su estructura de canales, es importante que las cosas sean sencillas, sobre todo si desea que se incorporen muchos usuarios. Resista el impulso de crear canales para cada situación, función o tema a fin de reducir al mínimo la necesidad de formación. Seleccione de 3 a 5 canales como mucho para empezar. Se pueden crear fácilmente canales adicionales a medida que surja la necesidad. De hecho, por el momento está bien usar solo el canal general.

#### <a name="steps-to-create-channels-for-teams"></a>Pasos para crear canales para los equipos

1. Busque el archivo **TeamsChannels.csv** en los recursos del archivo .zip.
1. Actualice la información en el archivo **TeamsChannels.csv** con la información específica de su organización. Tenga en cuenta las recomendaciones anteriores.
1. Busque el script **CreateTeamsChannels.ps1** en los recursos del archivo .zip.
1. Desde PowerShell, ejecute el script **TeamsChannels.ps1**

## <a name="create-teams-policies"></a>Cree directivas a los equipos

Como administrador de, puede usar las directivas de equipo en Microsoft Teams para controlar lo que los usuarios de su organización ven y pueden ver. Por ejemplo, puede controlar qué aplicaciones están fijadas en el raíl izquierdo en su Escritorio o en el Explorador Web, o en la barra inferior de los dispositivos móviles, para simplificar la experiencia del usuario final cuando incorpora una gran cantidad de usuarios. Algunas de estas directivas se pueden crear con PowerShell y otras se deben crear manualmente en la consola de administración de Teams.

*Discusión de prácticas recomendadas*: para cada una de las siguientes directivas, estamos eligiendo crear dos directivas: una para los Firstline Workers y otra para los Firstline Managers. Puede elegir crear tantos o tan pocos como quiera. Para la mayoría de los clientes, dos es un buen punto de partida, incluso si se asigna la misma configuración a cada grupo inicialmente. A medida que su experiencia con Teams crezca, puede elegir diferenciar más su experiencia y tener las dos directivas separadas ya creadas puede hacer eso más simple.

### <a name="create-teams-message-policies"></a>Cree directivas de mensajería de Teams

Las directivas de mensajería se usan para controlar qué características de mensajería en canales y chats están disponibles los usuarios en Microsoft Teams.

*Discusión de prácticas recomendadas*: aunque puede usar la directiva global predeterminada que se crea automáticamente, hemos optado por crear una directiva personalizada siguiendo estos pasos para ofrecer una experiencia más bloqueada, simple y diferenciada para los Firstline Managers y los Firstline Workers.

#### <a name="steps-to-create-teams-message-policies"></a>Pasos para crear directivas de mensajería de Teams

1. Busque **TeamsMessagingPolicies.csv** en los recursos del archivo .zip.
1. Actualice el archivo **TeamsMessagingPolicies.csv** con la información específica de su organización. Se puede encontrar información adicional sobre algunas de las distintas opciones [aquí](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).
1. Busque el script **CreateTeamsMessagePolicies.ps1** en los recursos.
1. Desde PowerShell, ejecute el script **TeamsMessagePolicies.ps1**

### <a name="create-teams-app-setup-policies"></a>Cree directivas de configuración de la aplicación Teams

Como administrador, puede usar las directivas de configuración de la aplicación para hacer lo siguiente:

- Personalice Teams para destacar las aplicaciones más importantes para sus usuarios. Elija las aplicaciones que desee fijar y configure el orden en que aparecen. Anclar aplicaciones le permite mostrar las aplicaciones que necesitan los usuarios de su organización, incluyendo aquellas creadas por terceros o por desarrolladores de su organización.
- Controle si los usuarios pueden anclar aplicaciones a Teams.

Las aplicaciones se anclan en la barra de aplicaciones. Esta es la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).

|Cliente de escritorio de Teams  |         |Cliente móvil de Teams  |
|---------|---------|---------|
|![Una captura de pantalla del cliente de escritorio de Teams con aplicaciones ancladas a la barra de *aplicaciones*.](media/FLW-Teams-Desktop-Client.png)         |         |![Una captura de pantalla del cliente de escritorio de Teams con aplicaciones ancladas a la barra inferior.](media/FLW-Teams-Mobile-Client.png) |

*Discusión de prácticas recomendadas*: puede administrar directivas de configuración de aplicación en el Centro de administración de Microsoft Teams. No se pueden crear con PowerShell. Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios. Los usuarios de su organización serán asignados automáticamente a la directiva global, a menos que cree y asigne una directiva personalizada. Para nuestros propósitos, estamos creando dos nuevas políticas para los Firstline Workers y Firstline Managers, con el fin de proporcionarles una experiencia más sencilla y racionalizada para facilitar la incorporación de un gran número de usuarios simultáneamente. Puede elegir personalizar la experiencia según las necesidades de su empresa.

#### <a name="create-the-firstline-manager-app-setup-policy"></a>Cree la directiva de configuración de la aplicación Firstline Manager

Se pueden personalizar las siguientes configuraciones para satisfacer las necesidades de su empresa. Hemos elegido algunas opciones recomendadas basándonos en las prácticas recomendadas y mejorar la facilidad de incorporación de nuevos usuarios a escala. Para obtener más información, haga clic [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. En el panel de navegación izquierda del centro de administración de Microsoft Teams, vaya a  **Directivas de ** > **configuración de aplicaciones de Teams**.
2. Haga clic en **Agregar**.  
3. Escriba un nombre y una descripción para la directiva. Por ejemplo: **directiva de configuración de la aplicación Firstline Manager**.
![Imagen de la directiva de configuración de la aplicación Firstline Manager.](media/FLW-FLM-App-Setup-Policy.png)

4. Deshabilite **Cargar aplicaciones personalizadas**.
5. Deshabilite **Permitir el anclaje de usuarios**.
![Permitir al usuario anclar la imagen del interruptor.](media/FLW-Allow-User-Pinning.png)

6. Si aún no aparece en la lista, agregue el **Turno** a la aplicación. Para obtener más información acerca de los **Turnos**, haga clic [aquí](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
![La pantalla "Agregar aplicaciones ancladas" muestra la aplicación "Turnos" junto al botón "Agregar".](media/FLW-Add-Pinned-Apps.png)

7. Quite las llamadas, si aparece. Nota: al quitar esta función no se deshabilitará para el usuario, sino que se evitará que aparezca en la barra de aplicaciones para simplificar la experiencia del usuario final.
8. Organiza las aplicaciones en el siguiente orden para dictar su orden en la barra de aplicaciones de Teams, y luego haz clic en  **Guardar**.
    1. Actividad
    1. Chat
    1. Teams
    1. Calendario
    1. Turne la ![Captura de pantalla de la lista de aplicaciones del administrador en orden.](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>Cree la directiva de configuración de la aplicación Firstline Worker

Se pueden personalizar las siguientes configuraciones para satisfacer las necesidades de su empresa. Hemos elegido algunas opciones recomendadas basándonos en las prácticas recomendadas y mejorar la facilidad de incorporación de nuevos usuarios a escala. Para obtener más información, haga clic [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. En el panel de navegación izquierda del centro de administración de Microsoft Teams, vaya a  **Directivas de ** > **configuración de aplicaciones de Teams**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva. Por ejemplo: **directiva de configuración de la aplicación Firstline Worker**.
![Imagen de la directiva de configuración de la aplicación Firstline worker.](media/FLW-FLW-App-Setup-Policy.png)

4. Deshabilite **Cargar aplicaciones personalizadas**.
5. Deshabilite **Permitir el anclaje de usuarios**.
![Permitir al usuario anclar la imagen del interruptor.](media/FLW-Allow-User-Pinning.png)

6. Si aún no aparece en la lista, agregue el **Turno** a la aplicación. Para obtener más información acerca de **Turnos**, haga clic aquí.
![La pantalla "Agregar aplicaciones ancladas" muestra la aplicación "Turnos" junto al botón "Agregar".](media/FLW-Add-Pinned-Apps.png)

7. Quitar Reuniones y Llamadas, en caso de que aparezcan. Nota: al quitar esta función no se deshabilitará para el usuario, sino que se evitará que aparezca en la barra de aplicaciones para simplificar la experiencia del usuario final.
8. Organiza las aplicaciones en el siguiente orden para dictar su orden en la barra de aplicaciones de Teams, y luego haz clic en  **Guardar**.
    1. Actividad
    1. Chat
    1. Teams
    1. Turne la ![Captura de pantalla de la lista de aplicaciones del trabajador en orden.](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-app-permission-policies"></a>Crear directivas de permisos de aplicación

Como administrador, puede usar las directivas de permisos de aplicación para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización. Puede permitir o bloquear todas las aplicaciones, o aplicaciones específicas publicadas por Microsoft, terceros y su organización. Cuando bloquee una aplicación, los usuarios que tienen la directiva no pueden instalarla desde la tienda de aplicaciones de Teams. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

*Discusión de prácticas recomendadas*: puede administrar directivas de configuración de aplicación en el Centro de administración de Microsoft Teams. No se pueden crear con PowerShell. Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Estamos creando dos nuevas políticas para Firstline Workers y Firstline Managers para nuestros propósitos, con el fin de proporcionarles una experiencia más segura y simplificada para facilitar la incorporación simultánea de un gran número de usuarios. Por supuesto, puede elegir la personalización de la experiencia según las necesidades de su empresa.

#### <a name="create-the-firstline-manager-app-permission-policy"></a>Crear la directiva de configuración de la aplicación Firstline Manager

Se pueden personalizar las siguientes configuraciones para satisfacer las necesidades de su empresa. Estas son algunas de las opciones recomendadas en base a las prácticas recomendadas para mejorar el nivel de incorporación fácil de los nuevos usuarios. Para más información, haga clic [aquí](teams-app-permission-policies.md).

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a  **Aplicaciones de Teams** > **Directivas de permisos**.
2. Haga clic en **Agregar**.
![Mostrar la página de la directiva de permisos de aplicaciones, con las secciones para aplicaciones de Microsoft, de terceros e inquilinos.](media/FLW-add-app-permission-policy.png)

3. Escriba un nombre y una descripción para la directiva. Por ejemplo: directiva de permisos de la aplicación Firstline Manager
4. En las aplicaciones de Microsoft, seleccione **Permitir todas las aplicaciones**.
5. En las aplicaciones de terceros, seleccione **Permitir todas las aplicaciones**.
6. En las aplicaciones de los inquilinos, seleccione **Permitir todas las aplicaciones**.
7. Haga clic en **Guardar**.

#### <a name="create-the-firstline-worker-app-permission-policy"></a>Crear la Directiva de permisos de la aplicación Firstline Worker

Se pueden personalizar las siguientes configuraciones para satisfacer las necesidades de su empresa. Estas son algunas de las opciones recomendadas en base a las prácticas recomendadas para mejorar el nivel de incorporación fácil de los nuevos usuarios. Para más información, haga clic [aquí](teams-app-permission-policies.md).

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a  **Aplicaciones de Teams** > **Directivas de permisos**.
2. Haga clic en **Agregar**.
![Mostrar la página de la directiva de permisos de aplicaciones, con las secciones para aplicaciones de Microsoft, de terceros e inquilinos.](media/FLW-add-app-permission-policy.png)

3. Escriba un nombre y una descripción para la directiva. Por ejemplo: directiva de permisos de la aplicación Firstline Worker.
4. En las aplicaciones de Microsoft, seleccione **Permitir todas las aplicaciones**.
5. En las aplicaciones de terceros, seleccione **Bloquear todas las aplicaciones**.
6. En las aplicaciones de los inquilinos, seleccione **Permitir todas las aplicaciones**.
7. Haga clic en **Guardar**.

## <a name="create-and-set-up-users"></a>Crear y configurar usuarios

### <a name="create-user-and-security-groups"></a>Cree usuarios y grupos de seguridad

Crear los usuarios en Azure AD es lo primero que necesita para trabajar con una gran cantidad de usuarios en Teams. Tenemos varias formas de aprovisionar a un gran número de usuarios, pero vamos a resaltar lo siguiente:

- Si estos usuarios ya existen en uno de los siguientes sistemas de RR.HH, use los siguientes vínculos para configurar el aprovisionamiento de los usuarios:
  - Factores de éxito de SAP: [Tutorial: configurar SAP SuccessFactors para el aprovisionamiento de usuarios de Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Día de laborable: [Tutorial: configurar el aprovisionamiento automático de usuarios para el día laborable](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Si tiene su información de usuario en otros sistemas, siga estos pasos.

Para administrar estos usuarios de forma más eficaz, debe crear dos grupos de seguridad para Firstline Workers y Firstline Managers, y aprovisionar estos usuarios en los grupos de seguridad directamente, siguiendo estos pasos:

1. Busque el archivo **SecurityGroups.csv** en los recursos del archivo .zip.
1. Actualice la información en el archivo **SecurityGroups.csv** con la información específica de su organización.
    1. Asegúrese de actualizar los campos **MessagePolicy**, **AppPermissionPolicy**, y **AppSetupPolicy** para asignar las directivas apropiadas que creó anteriormente.
    1. Asegúrese de actualizar el campo **LicensePlan** para reflejar la licencia que pretende dar a cada uno de estos usuarios. Para obtener más información sobre los nombres de los productos y los identificadores de los planes de servicio, revise la documentación [aquí](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. Busque el archivo **Users.csv** en los recursos del archivo .zip.
1. Actualice el archivo **Users.csv** con la información específica de su organización.
    1. De forma predeterminada, el script que hemos proporcionado creará un usuario con una contraseña temporal que debe cambiarse en el primer inicio de sesión. Si no desea utilizar la contraseña predeterminada, edite el script **CreateUsers.ps1** para cumplir con sus requisitos.
    1. Asegúrese de actualizar el campo SecurityGroup para reflejar la licencia que pretende dar a cada uno de estos usuarios.
1. Desde PowerShell, ejecute el script **CreateUsers.ps1** de los recursos.

### <a name="assign-licensing-to-users-by-group-based-licensing"></a>Asignar licencias a los usuarios a través de las licencias basadas en grupos

Los servicios en la nube pagados por Microsoft, como Office 365, Enterprise Mobility + Security, Dynamics 365 y otros productos similares, requieren licencias. Estas licencias se asignan a todos los usuarios que necesitan acceso a estos servicios. Para administrar las licencias, los administradores usan uno de los portales de administración (Office o Azure) y los cmdlets de PowerShell. Azure Active Directory (Azure AD) es la infraestructura subyacente que admite la administración de identidades para todos los servicios en la nube de Microsoft. Azure AD almacena información sobre los estados de asignación de licencias para los usuarios.

Para permitir el otorgamiento de licencias a escala, Azure AD ahora incluye licencias basada en grupo y, por este motivo, hemos creado los grupos de seguridad anteriormente en este artículo. Puede asignar una o más licencias de producto a un grupo. Azure AD se asegura de que se asignan las licencias a todos los miembros del grupo. Si se unen nuevos miembros al grupo se les asignarán las licencias adecuadas. Las licencias de los miembros que abandonan el grupo son eliminadas. Esta administración de licencias elimina la necesidad de automatizar la administración de licencias mediante PowerShell para reflejar los cambios en la estructura de organización y departamentales para cada usuario.

## <a name="assign-users-and-policies"></a>Asignar usuarios y directivas

### <a name="assigning-users-to-teams"></a>Asignación de usuarios a equipos

Ahora que ha creado los usuarios y creado los Teams, es hora de colocar todos los usuarios en los Teams adecuados.

1. Busque el archivo **Users.csv** en los recursos de archivo. zip y asegúrese de que tiene una asignación exacta a los equipos de este archivo.
1. Desde PowerShell, ejecute el script **AssignUserstoTeams.ps1** de los recursos del archivo. zip.

### <a name="assign-teams-policies-to-users"></a>Asigne las directivas de Teams a los usuarios

Ahora que ha creado los usuarios y las directivas para modificar su experiencia en Teams, es hora de asignar estas directivas a los usuarios correctos.

1. Busque el archivo **SecurityGroups.csv** en los recursos de archivo. zip y asegúrese de que tiene una asignación exacta de las directivas a los grupos.
1. Desde PowerShell, ejecute el script **AssignPoliciestoUsers.ps1** de los recursos del archivo. zip.

## <a name="test-and-validate"></a>Pruebe y valide

### <a name="check-for-errors"></a>Compruebe errores

Como ha ejecutado las secuencias de comandos anteriores, los errores o excepciones se escribieron en un archivo. csv ubicado en la carpeta logs de los recursos de archivo. zip. Este archivo puede ser utilizado para investigar cualquier problema que se haya producido.

Un ejemplo de excepción podría ser si intenta crear un equipo que ya existía en su espacio empresarial.

1. Busque la carpeta **Registros** y revisar cualquier archivo. csv que pueda contener. Si no hay ninguna excepción, es posible que no pueda encontrar un archivo de excepciones aquí.

### <a name="login-to-teams-with-a-test-user"></a>Inicie sesión en Teams con un usuario de prueba

Ahora que ya ha completado todos los pasos, es momento de verificar el trabajo que ha realizado.

1. Seleccione un usuario de la lista anterior y inicie sesión en Teams con las credenciales del usuario.
1. Verifique que el aspecto de los Teams es lo que esperaba. En caso contrario, revise el **Crear Directivas de Teams** y el **Asignar Directivas de Equipo a Usuarios** secciones.
1. Compruebe que el usuario se encuentra en el equipo correcto. En caso contrario, revise el **Crear y configurar usuarios** y **asignar usuarios a Teams** secciones.
