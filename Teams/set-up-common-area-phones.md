---
title: Configurar la licencia de Teléfono de área común
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Aprenda a configurar teléfonos de área común para vestíbulos, áreas de recepción y salas de conferencias '
ms.openlocfilehash: f3f3ee2c98e48a41bb12dcaa7fc461c623f49994
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045829"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Implementar teléfonos de área común para Microsoft Teams

Un teléfono de área común se coloca normalmente en un área como una sala de espera u otra área que está disponible para muchas personas para hacer una llamada; por ejemplo, una zona de recepción, sala de espera o teléfono de conferencia. Los teléfonos de área común han iniciado sesión con cuentas vinculadas a una licencia de Teléfono de área común.

Este artículo proporciona información general sobre cómo implementar y configurar teléfonos Teams como teléfonos de área comunes para espacios compartidos. Para obtener una experiencia de sala de reuniones más completa, incluida la audioconferencia, considere la posibilidad de comprar la licencia de Sala de reuniones dedicada con un dispositivo de sala de reuniones.

## <a name="overview"></a>Información general

La licencia de Teléfono de área común admite:

|                                           | Teléfono de área común                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Teléfono** &sup1;                   | &#x2714;                                          |
| **Audioconferencia**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **plan 1 de Azure Active Directory Premium** | &#x2714;                                          |
| **plan 2 de Exchange Online**                | &#x2714;  &sup3;                                  |
| **Disponibilidad mundial**                | &#x2714;                                          |
| **Disponibilidad del canal**                  | EA, EAS, EES, CSP, Web Direct, GCC, GCC-High, DoD |

&sup1; Anteriormente conocido como Sistema telefónico.

&sup2; Los teléfonos de área común pueden unirse a audioconferencias a través de un número de acceso telefónico proporcionado por el organizador de la reunión.  

&sup3; Solo funciones del correo de voz basado en la nube.

>[!NOTE]
> Las cuentas de teléfonos de área común objetos creados en Skype Empresarial Server no se pueden migrar a Microsoft Teams. Siga los pasos de este artículo para volver a crear esas cuentas para Teams y, si es necesario, migre la conectividad PTSN.

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

En primer lugar, debe comprar una licencia de Teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre los teléfonos certificados, ve a [Microsoft Teams dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. En la Centro de administración de Microsoft 365, ve a **Servicios** **de compra de facturación** > . 

2. Si la sección **Ver por categoría** aún no se muestra, ve a **Comprar de Microsoft** y selecciona **Ver productos**. A continuación, seleccione **Colaboración y comunicación**.  

3. En la lista de productos, busca **Área común Teléfono** y selecciona **Detalles**.

4. Escriba el número de licencias que necesita y seleccione **Comprar**.

>[!NOTE]
>Si usa Intune en su entorno y tiene reglas de acceso condicional que requieren el cumplimiento del dispositivo, tendrá que asignar una Azure Active Directory Premium Plan 1 y Intune licencia a la cuenta de dispositivo para el teléfono de área común.
>
>Los teléfonos de área comunes pueden verse afectados por reglas de acceso condicional y otras configuraciones de identidad, como la autenticación multifactor. Consulte Procedimientos [recomendados de autenticación para dispositivos Teams Android](devices/authentication-best-practices-for-android-devices.md) para obtener más información.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Paso 2: Crear una nueva cuenta de usuario y asignar licencias

### <a name="using-the-microsoft-365-admin-center"></a>Usar el Centro de administración de Microsoft 365

Si va a implementar más de un teléfono de área común a la vez, obtenga información sobre cómo crear cuentas y asignar licencias [con PowerShell](#using-powershell).

Si vas a implementar un dispositivo:

1. En la Centro de administración de Microsoft 365, vaya a **Usuarios** > **activos** > **Agregar un usuario**.

2. Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".

4. Escriba un nombre de usuario como "MainReception" o "Mainlobby".

5. Establece manualmente la contraseña de tu teléfono de área común para evitarlo. Para ello, desactive **Crear automáticamente una contraseña** y **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.  

    >[!Important]
    > Es muy recomendable establecer manualmente una contraseña para teléfonos de área común para evitar problemas de inicio de sesión para los usuarios finales.

6. Seleccione la ubicación de uso del dispositivo y asigne el Área común Teléfono licencia a la cuenta. Si se necesitan otras licencias, como Planes de llamadas, asígnelas.

>[!NOTE]
> No es necesario agregar una licencia de Sistema telefónico. Está incluida en la licencia del teléfono de área común.
>
>Si no usa Teléfono Microsoft enrutamiento directo del sistema o Conexión con operador, es posible que desee agregar licencias de planes de llamadas. Para obtener más información sobre las licencias, consulte [Microsoft Teams licencias complementarias](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Con PowerShell

Use PowerShell cuando desee crear y asignar licencias para más de una cuenta de usuario a la vez. Vea [Crear cuentas de usuario Microsoft 365 con PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) y [Asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) para obtener más información.

## <a name="step-3---set-policies-for-common-area-phones"></a>Paso 3: Establecer directivas para teléfonos de área comunes

Use directivas para controlar qué características están disponibles para los usuarios en teléfonos de área común.

>[!NOTE]
>Después de asignar una directiva, cierra sesión en el teléfono y vuelve a iniciarla. Una asignación de directiva puede tardar hasta una hora en surtir efecto.

### <a name="ip-phone-policies"></a>Directivas de teléfonos IP

Los teléfonos que hayan iniciado sesión con cuentas a las que se les haya asignado una licencia de área común Teléfono mostrarán la experiencia de usuario del área común.

Si desea invalidar la interfaz predeterminada de un teléfono, considere la posibilidad de crear una [directiva de teléfono IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true). Por ejemplo, si un teléfono de área común se usa en un área pública, establezca una directiva de teléfono IP para restringir la búsqueda en la Libreta global de direcciones de su organización y bloquear el servicio de escritorio rápido. Consulta [Establecer Teams Android interfaz de usuario de dispositivos](devices/Teams-Android-devices-user-interface.md) para obtener más información.

### <a name="calling-policies"></a>Directivas de llamada

Use directivas de llamada para habilitar llamadas privadas, mediante desvío de llamadas o llamadas simultáneas en teléfonos de área común. Consulte [Llamadas y desvío de llamadas en Teams](teams-calling-policy.md) para obtener más información.

De forma predeterminada, el parque de llamadas no está habilitado para los teléfonos de área común. Deberá crear una directiva para habilitarla. Consulte [Estacionar llamadas y recuperar en Microsoft Teams](call-park-and-retrieve.md) para obtener más información.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Paso 4: Adquirir y asignar números de teléfono

Consulte [Administrar los números de teléfono de su organización para](manage-phone-numbers-landing-page.md) obtener información sobre cómo adquirir y asignar números de teléfono en función de la opción de conectividad con RTC.

## <a name="step-5---sign-in"></a>Paso 5: Iniciar sesión

Después de crear y configurar una cuenta de usuario, puedes iniciar sesión en un teléfono. En función del número de teléfonos que implemente, tiene tres opciones de inicio de sesión:

- [Inicio de sesión local](#local-sign-in)
- [Iniciar sesión desde otro dispositivo](#sign-in-from-another-device)
- [Iniciar sesión con el Centro de administración de Teams](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Inicio de sesión local

Para iniciar sesión localmente con un nombre de usuario y contraseña: 

1. Activar el teléfono de área común

2. Selecciona **Iniciar sesión en este dispositivo**

3. Sigue las instrucciones de inicio de sesión en el dispositivo. Una vez que haya iniciado sesión, el teléfono mostrará la experiencia de usuario del teléfono de área común.

> [!NOTE]
> Si usa una directiva de configuración personalizada que desancla la aplicación de llamadas, el teclado de marcado no aparece en el Teléfono del área común. Para obtener más información sobre las directivas de configuración de Teams, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Iniciar sesión desde otro dispositivo

También puedes iniciar sesión en un teléfono de área común desde otro dispositivo mediante un código. Cuando inicies sesión de esta manera, deberás introducir el nombre de usuario y la contraseña en otro dispositivo, en lugar de en el teléfono en sí.

1. En primer lugar, en el teléfono de área común, busca el código que se muestra en la pantalla de inicio de sesión.

2. En otro dispositivo, ve a https://www.microsoft.com/devicelogin.

3. Escribe el código y sigue las instrucciones para completar el inicio de sesión.

### <a name="sign-in-using-the-teams-admin-center"></a>Iniciar sesión con el Centro de administración de Teams

Como administrador, puede aprovisionar e iniciar sesión de forma remota en teléfonos de área común desde el centro de administración de Teams. Este es el método de inicio de sesión más eficaz al implementar un gran número de teléfonos a la vez. Consulta [Aprovisionamiento remoto e inicia sesión en dispositivos Teams Android](devices/remote-provision-remote-login.md) para obtener más información.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado e iniciado sesión en teléfonos de área común para su organización, puede administrarlos en el Teams centro de administración. Consulta [Microsoft Teams: Administrar los dispositivos](devices/device-management.md) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Actualizar Microsoft Teams dispositivos de forma remota](devices/remote-update.md)
- [Administrar etiquetas de dispositivo Microsoft Teams](devices/manage-device-tags.md)
- [supervisión del estado del dispositivo Microsoft Teams](alerts/device-health-status.md)
