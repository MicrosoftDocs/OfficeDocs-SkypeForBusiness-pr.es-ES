---
title: Directivas de números gratuitos de audioconferencia
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Obtenga información sobre cómo audioconferencia en Microsoft 365 o Office 365 permite a los usuarios llamar a las reuniones desde sus teléfonos.
ms.openlocfilehash: 8fcc731f208dc3fecd42dd2c351714f67ad6a684
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732409"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>Configuración de la directiva de Audioconferencia para números de pago y gratuitos

## <a name="teams-audio-conferencing-policy"></a>Directiva de audioconferencia de Teams

Use las directivas de audioconferencia para administrar los números de pago y gratuitos de audioconferencia que se mostrarán en las invitaciones de reunión creadas por usuarios de su organización. Puede usar una de las dos directivas creadas automáticamente o crear y asignar directivas personalizadas. Las dos directivas creadas automáticamente son globales (valor predeterminado para toda la organización) y AllowTollFreeDialinFalse (asignadas a todos los usuarios existentes dentro de la organización que no están habilitados para números de acceso telefónico gratuitos). Puede administrar las directivas de audioconferencia en el Centro de administración de Microsoft Teams o mediante [PowerShell](teams-powershell-overview.md).

- La configuración de AllowTollFreeDialin ya no se puede administrar para un usuario individual a través del Centro de administración de Teams o PowerShell. Los administradores de inquilinos solo podrán administrar esta configuración mediante la nueva directiva de audioconferencia.
- La directiva global no se puede modificar desde el Centro de administración de Teams.

> [!NOTE]
> Las directivas de audioconferencia personalizadas no son compatibles con los clientes habilitados para Skype Empresarial reuniones hospedadas regionalmente. Los clientes habilitados para reuniones hospedadas regionalmente pueden administrar la configuración de Audioconferencia de los usuarios a través de su configuración predeterminada. La configuración predeterminada de audioconferencia de los usuarios se puede cambiar en el Centro de Administración de Teams yendo a **Usuarios** -> **Administrar usuarios** -> **Seleccionando Cuenta de usuario** -> .

Cuando se habilita una directiva de audioconferencia de Teams en el inquilino, habrá dos directivas creadas automáticamente disponibles en el inquilino. Las dos directivas creadas automáticamente y su configuración predeterminada son:

### <a name="global-org-wide-default"></a>Global (valor predeterminado para toda la organización)

En esta directiva, el valor de **AllowTollfreedialin** se establecerá en ON y no habrá ningún número de teléfono definido en la directiva. Esta será la directiva predeterminada para todos los usuarios del inquilino que en el momento del lanzamiento tengan **AllowTollfreedialin** establecido **en Activado**.
Dado que la directiva no tiene ningún número de teléfono definido, cuando los usuarios de esta directiva creen una reunión de Teams, los números de teléfono disponibles en la reunión serán los mismos que los usuarios tenían antes de la directiva. Estos números de teléfono suelen tener como valor predeterminado el país o la ubicación del usuario, a menos que el administrador de inquilinos los cambie para usuarios individuales.

Por ejemplo, si un usuario basado en Alemania tenía asignados números de teléfono de pago y gratuitos de Alemania antes del inicio de la directiva de audioconferencia, al iniciarlo se le asignará la directiva global y los números de teléfono que seguirán viendo en la invitación a la reunión serán los mismos que antes de que se aplicara la directiva (es decir,  los números de pago y gratuitos alemanes). Un usuario final no verá ningún cambio cuando se inicie la directiva. Sin embargo, si un administrador de inquilinos modifica la directiva global e incluye números de teléfono específicos en la directiva que son diferentes de antes, todos los usuarios de la directiva solo verán los números de teléfono que se incluyen en la directiva en las reuniones que programen.

> [!NOTE]
> Si, en lugar de modificar la directiva global, un administrador de inquilinos crea una directiva personalizada y la aplica a los usuarios, la configuración definida en la directiva personalizada será la que verán los usuarios finales en las invitaciones de reunión.

Por ejemplo, si la directiva personalizada tiene "AllowTollFreeDialinFalse" y no tiene ningún número de teléfono definido, los usuarios de esta directiva no podrán tener números de teléfono gratuitos y, dado que no se define ningún número de teléfono en la directiva, el número de teléfono de pago que se usará en las invitaciones de reunión creadas por dichos usuarios será los mismos números de teléfono que los usuarios tenían antes de la directiva. Estos números de teléfono suelen tener como valor predeterminado el país o la ubicación del usuario, a menos que el administrador de inquilinos los cambie para usuarios individuales.

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

En esta directiva, el valor de **AllowTollfreedialin** se establecerá en **Desactivado** y no habrá ningún número de teléfono definido en la directiva. Esta será la directiva predeterminada para todos los usuarios del inquilino que, en el momento del lanzamiento, tengan **AllowTollfreedialin** establecido en **Desactivado**.

Dado que la directiva no tiene ningún número de teléfono definido, cuando los usuarios de esta directiva creen una reunión de equipo, los números de teléfono que estarán disponibles en la reunión serían los mismos números de teléfono que los usuarios tenían antes de la directiva. Estos números de teléfono suelen estar predeterminados en el país, la región o la ubicación del usuario, a menos que el administrador de inquilinos haya cambiado esto para usuarios individuales.

Por ejemplo, si un usuario basado en Alemania tenía asignado un número de teléfono de pago de Alemania antes del lanzamiento de una directiva de Audioconferencia, al iniciarlo se le asignará la directiva "AllowTollfreedialinFalse" y los números de teléfono que seguirán viendo en la invitación a la reunión serán los mismos que antes (es decir, el número de pago de Alemania). Un usuario final no verá ningún cambio cuando se inicie la directiva. Sin embargo, si un administrador de inquilinos modifica la directiva **AllowTollfreedialinFalse** e incluye números de teléfono específicos en la directiva, todos los usuarios de la directiva solo verán los números de teléfono incluidos en la directiva en las reuniones que programen.

## <a name="create-a-custom-audio-conferencing-policy"></a>Crear una directiva de audioconferencia personalizada

Información general de los pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Reuniones > Audioconferencia.
1. Seleccione Agregar.
1. Escriba el nombre y la descripción de la directiva. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres.
1. Seleccione la configuración que quiera usar.
1. Seleccione Guardar.

Por ejemplo, puede tener un grupo de usuarios que periódicamente tienen reuniones con participantes de más de un país. En nuestro ejemplo, los participantes son de Canadá, Botsuana y Singapur y todos quieren unirse a la reunión mediante audioconferencia marcando un número de teléfono. Puede crear una nueva directiva personalizada denominada "Canadá Botsuana Singapur" y seleccionar los números de teléfono de estos tres países para incluirlos en la directiva a través de la opción **Agregar un número de teléfono** y guardar esta directiva. Después, puede asignar esta directiva a los usuarios necesarios.

Esto garantiza que los números de teléfono que seleccionó para Canadá, Botsuana y Singapur se incluirán en las invitaciones a reuniones creadas por los usuarios de esta directiva.

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>Instrucciones paso a paso sobre la creación de una directiva personalizada basada en el ejemplo

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Audioconferencia** **de** >  reuniones.
2. Seleccione **Agregar**.
3. Escriba el nombre y la descripción de la directiva. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres.
4. Elija si desea Incluir números gratuitos en reuniones creadas por usuarios de esta directiva. Si establece esta opción **en Activado** , podrá agregar números de teléfono gratuitos en esta directiva.
5. Selecciona Agregar un número de teléfono.
6. Se abrirá un panel a la derecha de la pantalla, que contiene el cuadro **Buscar por ubicación** .
7. Escriba Canadá y seleccione un número de teléfono de Canadá en los resultados.
8. Seleccione **Agregar**.
9. Repita los pasos 6 y 7 del mismo modo para buscar y agregar números de teléfono de Botsuana y Singapur.
10. Seleccione números gratuitos si ha activado la opción **Incluir números gratuitos en las reuniones creadas por los usuarios de esta directiva** en el paso 4.
11. Seleccione **Agregar** en la esquina inferior derecha del panel. Se mostrarán los números de teléfono de los tres países que seleccionó.
12. Hay una columna de jerarquía que determina el orden en que se mostrarán los números de teléfono en las invitaciones a reuniones creadas por los usuarios de esta directiva. Para cambiar el orden, selecciona un número de teléfono y muévelo hacia arriba o hacia abajo con los botones **Subir** y **Bajar** respectivamente.
13. Una vez que haya puesto los números de teléfono en el orden que prefiera, seleccione **Guardar**.
14. Se crea la directiva personalizada denominada "Canadá Botsuana Singapur".
15. Una vez completada la creación, puede asignar esta directiva a los usuarios.

## <a name="edit-a-meeting-policy"></a>Editar una directiva de reunión

Puede editar las directivas personalizadas que cree. (Tenga en cuenta que la directiva global no se puede editar desde el Centro de administración de Teams)

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Audioconferencia** **de** >  reuniones.
1. Elija la directiva que quiera editar seleccionando a la izquierda del nombre de la directiva y, a continuación, **editar.**
1. Realice modificaciones.
1. Seleccione **Guardar**.

> [!NOTE]
> No puede eliminar una directiva si tiene usuarios asignados. Tendrás que asignar una directiva diferente a todos los usuarios afectados y, a continuación, podrás eliminar la directiva original.

## <a name="assign-a-meeting-policy-to-users"></a>Asignar una directiva de reunión a los usuarios

> [!IMPORTANT]
> Una vez que se aplica una nueva directiva de Audioconferencia a un usuario, los números de teléfono definidos en la directiva solo estarán disponibles en las reuniones nuevas creadas por el usuario con esta directiva. Las reuniones antiguas y periódicas programadas antes de la directiva seguirán mostrando la configuración antigua, por ejemplo, un número de pago y otro gratuito (si se ha habilitado la opción de pago para ese usuario). Un escenario aquí podría ser que un usuario tuviera **activado Permitir gratuito** y tuviera asignado un número gratuito y crear reuniones periódicas para el futuro. En este escenario, si crea una directiva personalizada con AllowTollfreeDialIn **desactivado y** lo aplica a este usuario, las reuniones nuevas creadas por este usuario no incluirán números gratuitos, pero las reuniones antiguas y periódicas seguirán mostrando números gratuitos. Por lo tanto, si los autores de llamadas marcan este número gratuito para unirse a la reunión, se producirá un error en la llamada porque la llamada gratuita ahora está deshabilitada para este usuario debido a la directiva. Para evitar esto, puede migrar las reuniones antiguas de los usuarios después de asignarles la nueva directiva de audioconferencia. Revise [Usar el servicio de migración de reuniones (MMS).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

Puede asignar una directiva directamente a los usuarios o a un grupo del que los usuarios sean miembros (si se admite para el tipo de directiva), ya sea de forma individual o en números mayores a través de una asignación por lotes (si se admite para el tipo de directiva).

Para obtener información sobre las diferentes maneras en que puede asignar directivas a los usuarios, vea [Asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md).

> [!NOTE]
> Un usuario solo puede tener asignada una directiva de audioconferencia a la vez.

> [!IMPORTANT]
> Los números de teléfono asignados pueden tardar hasta 24 horas en aparecer en la invitación a la reunión. Si no ves números actualizados, espera al menos 24 horas antes de ponerte en contacto con el servicio de soporte técnico.

### <a name="known-issue"></a>Problema conocido

Al iniciar una reunión con la opción **Reunirse ahora** de Microsoft Teams > Calendario > Reunirse con Mow, si selecciona los puntos suspensivos ... y, a continuación, información de la reunión, habrá un problema con la parte inferior de la sección **en O llamar en (solo audio)**. Se mostrarán todos los números de teléfono definidos en la directiva, pero la alineación de los números dificulta la lectura.
