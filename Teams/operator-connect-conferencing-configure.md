---
title: Configurar operador Conectar conferencias
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre cómo configurar operador Conectar conferencias.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257555"
---
# <a name="configure-operator-connect-conferencing"></a>Configurar operador Conectar conferencias

En este artículo se detalla cómo configurar las conferencias Conectar operador para su organización y los usuarios.

Antes de configurar Conectar conferencias de operadores, lea Plan para operadores [Conectar conferencias](operator-connect-conferencing-plan.md) para obtener información sobre las ventajas y los requisitos de licencia.

Los temas tratados en este artículo incluyen:

- [Configurar un operador](#set-up-an-operator)
- [Adquirir números para el puente de audioconferencia](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Enviar llamadas salientes desde Microsoft Teams reuniones a través de un operador](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Administrar los operadores](#manage-your-operators)
- [Liberar números de su puente de audioconferencia](#release-numbers-from-your-audio-conferencing-bridge)
- [Información adicional sobre la administración de audioconferencias de Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurar un operador

Puede configurar, editar y quitar operadores en el centro Teams administración. En el panel de navegación izquierdo, vaya **a Operadores de > voz.**

Para configurar un operador:

1. **Elija un operador.**   En la  **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de   voz. A continuación, seleccione el operador que desea usar. Para operador Conectar conferencias, compruebe que el operador tiene **conferencias** enumeradas como un producto disponible.

2. **Seleccione países.**   En  **Configuración del operador,** seleccione los países que desea habilitar con el operador seleccionado.

3. **Proporcionar información de contacto**   La información de contacto, incluido su nombre completo y su dirección de correo electrónico, se compartirá con su operador. Puede cambiar esta información más adelante. Además, deberá proporcionar el tamaño de la compañía, con la opción de proporcionar su número de teléfono. Los operadores usan esta información para ponerse en contacto con usted con más detalles sobre Conectar conferencias.

4. Aceptar el aviso de transferencia de datos.

5. **Agregue el operador.**   Seleccione  **Agregar como mi operador** para   guardar.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Adquirir números para el puente de audioconferencia

El puente de audioconferencia de su organización incluye números de teléfono disponibles para todos los usuarios de su organización para unirse Microsoft Teams reuniones con números de teléfono RTC. Puede ver los números de teléfono asociados con el puente de audioconferencia de su organización en el Centro de administración de Teams en Reuniones **> puentes de conferencia.**

Para adquirir números de teléfono para el puente de audioconferencia, siga estos pasos:

1. **Suscripción estándar de audioconferencia o Conectar licencia de conferencias.** Los usuarios que necesitan números de operador Conectar conferencia para unirse a las reuniones que organizan deben tener asignada una licencia de suscripción estándar de audioconferencia o una licencia de conferencia de operador Conectar. Para obtener más información, vea [Planear la conferencia de Conectar operador.](operator-connect-conferencing-plan.md)

2. **Adquirir números.**   Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vaya al Microsoft 365 [de Conectar operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino.](/onedrive/find-your-office-365-tenant-id) Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el centro Teams de administración yendo a Números **> Teléfono voz.**

3. **Asigne números al puente de audioconferencia.** Puede asignar números a su puente de audioconferencia desde el centro de administración de Teams en Reuniones **> de conferencias > Agregar**. Para obtener más información, vea [Cambiar los números de teléfono en el puente de audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

>[!NOTE]
>No puede asignar números de operador Conectar conferencia como números predeterminados de un puente. Una vez que se haya asignado un número de teléfono al puente de conferencias de audio, el número se mostrará en la página Buscar un número **local** que se incluye en las invitaciones a reuniones de los usuarios de su organización con una licencia de audioconferencia o una licencia de operador Conectar conferencias.
>
>Para enrutar las llamadas [**salientes**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) a través de un operador, vea la sección Enviar llamadas salientes desde Teams reuniones a través de un operador más abajo en este artículo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios

 Este paso es opcional.

Los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones de reunión cuando programan una reunión. Puede actualizar los números de teléfono incluidos en las invitaciones de reunión de los usuarios en el Centro de administración de Teams en Usuarios **> Administrar usuarios.** Para actualizar los números de teléfono incluidos en las invitaciones de reunión de los usuarios, seleccione el usuario y **seleccione Editar** en la sección **Audioconferencia.**

Una vez aplicados los cambios, las nuevas invitaciones a reuniones de los organizadores incluirán los nuevos números de teléfono predeterminados. Sin embargo, las invitaciones a reuniones existentes que se programaron antes del cambio conservarán los números predeterminados originales.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Enviar llamadas salientes desde Microsoft Teams reuniones a través de un operador

Si tiene una suscripción a Microsoft AudioConferencing Standard o una licencia de Operador Conectar Conferencias, puede configurar el servicio de audioconferencia para enrutar todas o un conjunto de llamadas salientes desde reuniones de Teams a través de su operador configurando una directiva de enrutamiento de audioconferencias.

>[!NOTE]
>Con un operador Conectar licencia de conferencia, las llamadas salientes solo pueden pasar por el operador. Si tiene licencias de Conectar de conferencia, debe configurar el servicio como se describe a continuación para habilitar las llamadas salientes de Teams reuniones a números de teléfono.

Puede aplicar directivas de enrutamiento de audioconferencia en el nivel de usuario, lo que significa que el operador solo enruta las llamadas salientes de Teams reuniones organizadas por los usuarios con la directiva asociada. También puede aplicar estas directivas a nivel global, lo que significa que el operador enruta las llamadas salientes desde Teams reuniones organizadas por todos los usuarios de su organización.

Con PowerShell, cree la nueva directiva de enrutamiento de audioconferencias de su organización. Para especificar un operador como la ruta principal para las llamadas salientes desde Teams reuniones, siga los pasos siguientes con los comandos de PowerShell indicados:

1. [Paso 1: Agregar una nueva cadena a la directiva Uso de RTC en línea](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Paso 2: Crear una nueva directiva de ruta de voz en línea](#step-2-create-a-new-online-voice-route-policy)
3. [Paso 3: Crear una nueva directiva de enrutamiento de audioconferencias en línea](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Paso 4: Asignar la nueva directiva a los usuarios](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Paso 1: Agregar una nueva cadena a la directiva Uso de RTC en línea

Lea [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) para obtener más información sobre el uso de este cmdlet.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Paso 2: Crear una nueva directiva de ruta de voz en línea

Lea [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) para obtener más información sobre el uso de este cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Paso 3: Crear una nueva directiva de enrutamiento de audioconferencias en línea

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Paso 4: Asignar la nueva directiva a los usuarios

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>Para establecer una directiva de enrutamiento de audioconferencia como global y aplicarla a todos los usuarios de su organización, puede usar el ``-Global`` parámetro en lugar del ``-Identity`` parámetro. Por ejemplo, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` .

Al crear una directiva de enrutamiento de audioconferencia y aplicarla a un usuario, el operador que proporciona el número de teléfono especificado en las rutas de parámetro Teams llamadas salientes a números de teléfono ``BridgeSourcePhoneNumber`` RTC. Además, el parámetro especifica el número de teléfono que se usará como número de teléfono de identificación de línea de llamadas de llamadas salientes a ``BridgeSourcePhoneNumber`` números de teléfono RTC.

El patrón especificado en el formulario es de regex y especifica qué llamadas se enrutar ``NumberPattern`` a través del operador. El ``"\d+"`` patrón del ejemplo anterior coincide con todas las llamadas salientes de Teams reuniones. También puede establecer el parámetro NumberPattern como , que coincide con los números marcados con los siguientes formatos: +1 425 XXX XX XX o +1 206 XXX XX XX, o , que coincide con los números marcados con el siguiente  ``“^\+1(425|206)(\d{7})$”`` ``“^\+1(\d{10})$”`` formato: +1 425 XXX XX XX.

Una vez que asigne una directiva de enrutamiento de audioconferencias a un usuario, todas las llamadas desde sus reuniones a un  número de teléfono que coincida con el regex especificado en sus rutas de directiva de enrutamiento de audioconferencias a través de su operador, incluida Llamarme a llamadas y llamadas iniciadas a través de la opción Invitar a alguien o marcar **un** número de reunión.

## <a name="manage-your-operators"></a>Administrar los operadores

Desde la **pestaña Mis operadores,** puede ver los operadores, su estado y   realizar los siguientes cambios en las selecciones:

- Administrar servicios de operadores por país
- Suspender un operador
- Quitar un operador

>[!NOTE]
>Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios y el puente de audioconferencia y, después, ponerse en contacto con el operador para liberar los números.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Liberar números de su puente de audioconferencia

Para liberar números de teléfono desde el puente de audioconferencia desde el Centro de administración de Teams, vea Pasos cuando está **desasignando** un número de teléfono de servicio para un puente de conferencia en Cambiar los números de teléfono en el puente de [audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Información adicional sobre la administración de audioconferencias de Microsoft

Para obtener información adicional sobre cómo administrar Las audioconferencias de Microsoft para su organización, vea los siguientes artículos:

- Administrar la configuración del servicio de audioconferencia de Microsoft para su [organización: Administrar](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) la configuración de audioconferencia de su organización en Microsoft Teams

- Administrar la configuración del servicio de audioconferencia de Microsoft de los usuarios de su [organización:](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) Administrar la configuración de audioconferencia para un usuario en Microsoft Teams

- Cambiar los idiomas del operador automático de los números de teléfono de audioconferencia: [Establecer idiomas](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) de operador automático para conferencias de audio en Microsoft Teams
