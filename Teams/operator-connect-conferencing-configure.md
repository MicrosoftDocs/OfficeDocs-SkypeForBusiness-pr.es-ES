---
title: Configurar Conexión de conferencia con operador
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
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Más información sobre cómo configurar Conexión de conferencia con operador.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31c66e2621051ed96c13d6f414eec9dadb02495
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585077"
---
# <a name="configure-operator-connect-conferencing"></a>Configurar Conexión de conferencia con operador

En este artículo se detalla cómo configurar Conexión de conferencia con operador para su organización y los usuarios.

Antes de configurar Conexión de conferencia con operador, lea [Plan de Conexión de conferencia con operador](operator-connect-conferencing-plan.md) para obtener información sobre los requisitos de licencias y ventajas.

Los temas tratados en este artículo incluyen:

- [Configurar un operador](#set-up-an-operator)
- [Adquirir números para el puente de Audioconferencia](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Enviar llamadas salientes desde las reuniones de Microsoft Teams a través de un operador](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Administrar los operadores](#manage-your-operators)
- [Liberar números del puente de Audioconferencia](#release-numbers-from-your-audio-conferencing-bridge)
- [Información adicional sobre la administración de audioconferencias de Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurar un operador

Puede configurar, editar y quitar operadores en el Centro de administración de Teams. En el panel de navegación izquierdo, vaya a **Operadores de > de voz**.

Para configurar un operador:

1. **Elige un operador.** En la pestaña **Todos los operadores** , filtre los operadores disponibles por región o servicio para encontrar el operador adecuado para sus necesidades de voz. A continuación, selecciona el operador que quieras usar. Por Conexión de conferencia con operador, compruebe que su operador ha enumerado **Conferencia** como un producto disponible.

2. **Seleccione países.** En **Configuración del operador**, selecciona los países que quieras habilitar con el operador seleccionado.

3. **Proporcionar información de contacto** Su información de contacto, incluyendo su nombre completo y dirección de correo electrónico, se compartirá con su operador. Puede cambiar esta información más adelante. Además, tendrás que proporcionar el tamaño de la empresa, con la opción de proporcionar tu número de teléfono. Los operadores usan esta información para ponerse en contacto con usted con más detalles sobre Conexión de conferencia con operador.

4. Acepta el aviso de transferencia de datos.

5. **Agrega tu operador.** Selecciona **Agregar como mi operador** para guardar.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Adquirir números para el puente de Audioconferencia

El puente de audioconferencia de su organización incluye números de teléfono disponibles para que todos los usuarios de la organización se unan a las reuniones de Microsoft Teams con números de teléfono RTC. Puede ver los números de teléfono asociados al puente de Audioconferencia de su organización en el Centro de Administración de Teams en **Reuniones > Puentes de conferencia.**

Para adquirir números de teléfono para el puente de Audioconferencia, siga estos pasos:

1. **Audioconferencia Estándar o licencia de Conexión de conferencia con operador.** Los usuarios que necesitan números de Conexión de conferencia con operador para unirse a las reuniones que organizan necesitan tener asignada una licencia de suscripción de Audioconferencia Estándar o una licencia de Conexión de conferencia con operador. Para obtener más información, consulte [Plan de Conexión de conferencia con operador](operator-connect-conferencing-plan.md).

2. **Adquirir números.** Ve al sitio web de tu operador para pedir y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, ve al [directorio Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id). Una vez que el operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**.

3. **Asigne números al puente de Audioconferencia.** Puede asignar números a su puente de Audioconferencia desde el Centro de administración de Teams en **Reuniones > Puentes de conferencia > Agregar**. Para obtener más información, vea [Cambiar los números de teléfono en el puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>No puede asignar números de Conexión de conferencia con operador como números predeterminados de un puente. Una vez asignado un número de teléfono al puente de Audioconferencia, el número se mostrará en la **página Buscar un número local** incluido en las invitaciones de reunión de usuarios de su organización con una licencia de Audioconferencia o una licencia de Conexión de conferencia con operador.
>
>Para redirigir las llamadas salientes a través de un operador, consulte la sección [**Envío de llamadas salientes desde reuniones de Teams a través de un operador**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) más adelante en este artículo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios

 Este paso es opcional.

Los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones a reuniones cuando programa una reunión. Puede actualizar los números de teléfono incluidos en las invitaciones de reunión de los usuarios del Centro de Administración de Teams **en Usuarios > Administrar usuarios**. Para actualizar los números de teléfono incluidos en las invitaciones de reunión de los usuarios, seleccione el usuario y seleccione **Editar** en la sección **Audioconferencia** .

Después de aplicar los cambios, las nuevas invitaciones de reunión de los organizadores incluirán los nuevos números de teléfono predeterminados. Sin embargo, las invitaciones de reunión existentes que se programaron antes del cambio conservarán los números predeterminados originales.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Enviar llamadas salientes desde las reuniones de Microsoft Teams a través de un operador

Si tiene una suscripción estándar de Audioconferencia de Microsoft o una licencia de Conexión de conferencia con operador, puede configurar el servicio de Audioconferencia para redirigir todas las llamadas salientes o un conjunto de llamadas salientes desde las reuniones de Teams a través de su operador configurando una directiva de enrutamiento de audioconferencia.

>[!NOTE]
>Con una licencia de Conexión de conferencia con operador, las llamadas salientes solo pueden realizarse a través de su operador. Si tiene licencias de Conexión de conferencia con operador, debe configurar el servicio como se describe a continuación para habilitar las llamadas salientes de las reuniones de Teams a los números de teléfono.

Puede aplicar directivas de enrutamiento de audioconferencia en el nivel de usuario, lo que significa que su operador solo enruta las llamadas salientes de reuniones de Teams organizadas por usuarios con la directiva asociada. También puede aplicar estas directivas a nivel global, lo que significa que su operador enruta las llamadas salientes desde reuniones de Teams organizadas por todos los usuarios de su organización.

Con PowerShell, cree la nueva directiva de enrutamiento de audioconferencia de su organización. Para especificar un operador como la ruta principal para las llamadas salientes desde las reuniones de Teams, siga los pasos siguientes con los comandos de PowerShell indicados:

1. [Paso 1: Agregar una nueva cadena a la directiva de uso de RTC en línea](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Paso 2: Crear una nueva directiva de ruta de voz en línea](#step-2-create-a-new-online-voice-route-policy)
3. [Paso 3: Crear una nueva directiva de enrutamiento de audioconferencia en línea](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Paso 4: Asignar la nueva directiva a los usuarios](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Paso 1: Agregar una nueva cadena a la directiva de uso de RTC en línea

Lea [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) para obtener más información sobre el uso de este cmdlet.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Paso 2: Crear una nueva directiva de ruta de voz en línea

Lea [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) para obtener más información sobre el uso de este cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Paso 3: Crear una nueva directiva de enrutamiento de audioconferencia en línea

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Paso 4: Asignar la nueva directiva a los usuarios

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>Para establecer una directiva de enrutamiento de Audioconferencia como global y aplicarla a todos los usuarios de su organización, puede usar el ``-Global`` parámetro en lugar del ``-Identity`` parámetro. Por ejemplo, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

Al crear una directiva de enrutamiento de audioconferencia y aplicarla a un usuario, el operador que proporciona el número de teléfono especificado en el ``BridgeSourcePhoneNumber`` parámetro enruta las llamadas salientes de Teams a números de teléfono RTC. Además, el ``BridgeSourcePhoneNumber`` parámetro especifica el número de teléfono que se usará como número de teléfono de identificación de línea de llamadas de las llamadas salientes a los números de teléfono RTC.

El patrón especificado en el ``NumberPattern`` es de formulario regex y especifica las llamadas que se redirigirán a través de su operador. El ``"\d+"`` patrón del ejemplo anterior coincide con todas las llamadas salientes de las reuniones de Teams. También puede establecer el parámetro NumberPattern como  ``"^\+1(425|206)(\d{7})$"``, que coincide con los números marcados con los siguientes formatos: +1 425 XXX XX XX o +1 206 XXX XX XX, o ``"^\+1(\d{10})$"``, que coincida con los números marcados con el siguiente formato: +1 425 XXX XX XX.

Una vez que asigne una directiva de enrutamiento de audioconferencia a un usuario, todas las llamadas desde sus reuniones a un número de teléfono que coincida con la regex especificada en la directiva de enrutamiento de Audioconferencia se enruta a través de su operador, incluyendo **Llamarme a** llamadas y llamadas iniciadas mediante la opción **Invitar a alguien o marcar un número** de reunión.

## <a name="manage-your-operators"></a>Administrar los operadores

En la pestaña **Mis operadores** , puede ver sus operadores, su estado y realizar los cambios siguientes en sus selecciones:

- Administrar los servicios del operador por país
- Suspender un operador
- Quitar un operador

>[!NOTE]
>Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios y el puente de Audioconferencia y, a continuación, ponerse en contacto con el operador para liberar los números.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Liberar números del puente de Audioconferencia

Para liberar números de teléfono del puente de Audioconferencia desde el Centro de administración de Teams, vea **Pasos para cancelar la asignación de un número de teléfono de servicio para un puente de conferencia** en [Cambiar los números de teléfono en el puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge).

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Información adicional sobre la administración de audioconferencias de Microsoft

Para obtener información adicional sobre cómo administrar audioconferencias de Microsoft para su organización, vea los siguientes artículos:

- Administrar la configuración del servicio de audioconferencia de Microsoft para su organización: [Administrar la configuración de Audioconferencia de su organización en Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Administrar la configuración del servicio de Audioconferencia de Microsoft de los usuarios de su organización: [Administrar la configuración de Audioconferencia para un usuario en Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Cambiar los idiomas del operador automático de los números de teléfono de audioconferencia: [Establecer los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
