---
title: Configurar la licencia de área Teléfono común
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
description: 'Obtenga información sobre cómo configurar teléfonos de área común para lobbies, áreas de recepción y salas de conferencias '
ms.openlocfilehash: 313a17d1829c8f3584ec5fb7f37e5f1ec49231d0
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456943"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Implementar teléfonos de área comunes para Microsoft Teams

Un teléfono de área común normalmente se coloca en un área como una sala de espera u otra área que está disponible para muchas personas para realizar una llamada; por ejemplo, un área de recepción, una sala de espera o un teléfono de conferencia. Los teléfonos de área común han iniciado sesión con cuentas vinculadas a una licencia de Teléfono común.

En este artículo se proporciona información general sobre cómo implementar y configurar Teams teléfonos como teléfonos de área comunes para espacios compartidos. Para obtener una experiencia más completa en la sala de reuniones, incluidas las audioconferencias, considere la posibilidad de comprar la licencia de Sala de reuniones dedicada con un dispositivo de sala de reuniones.

## <a name="overview"></a>Información general

La licencia de Teléfono común es compatible con: 


| &nbsp;  |  Teléfono de área común  |
|---------|---------|
|Skype Empresarial |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema telefónico |    &#x2714; |
|Audioconferencia |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilidad mundial |       &#x2718; &sup2;  |
|Disponibilidad del canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión

&sup2; No disponible en nubes soberanas  

>[!NOTE]
> Las cuentas de objetos de teléfonos de área común Skype Empresarial Server no se pueden migrar a Microsoft Teams. Siga los pasos de este artículo para volver a crear esas cuentas Teams y, si es necesario, migrar la conectividad de PTSN.

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

En primer lugar, debe comprar una licencia de área Teléfono común (CAP) y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre teléfonos certificados, ve a [Microsoft Teams dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. En el Centro de administración de Microsoft 365, vaya a **BillingPurchase** >  services. 

2. Si la **sección Ver por** categoría aún no se muestra, vaya a **Comprar en Microsoft** y seleccione **Ver productos**. A continuación, **seleccione Colaboración y comunicación**.  

3. En la lista de productos, busque **Área común Teléfono** y seleccione **Detalles**.

4. Escriba el número de licencias que necesita y seleccione **Comprar**.

>[!NOTE]
>Si usa Intune en su entorno y tiene reglas de acceso condicional que requieren el cumplimiento del dispositivo, deberá asignar una licencia del Plan 1 de Azure Active Directory Premium e Intune a la cuenta del dispositivo para el teléfono de área común.
>
>Las reglas de acceso condicional y otras configuraciones de identidad pueden afectar a los teléfonos de área común, como la autenticación multifactor. Consulte [Procedimientos recomendados de autenticación Teams dispositivos Android](devices/authentication-best-practices-for-android-devices.md) para obtener más información.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Paso 2: Crear una nueva cuenta de usuario y asignar licencias

### <a name="using-the-microsoft-365-admin-center"></a>Usar la Centro de administración de Microsoft 365

Si va a implementar más de un teléfono de área común a la vez, obtenga información sobre cómo crear cuentas y asignar licencias [con PowerShell](#using-powershell).

Si va a implementar un dispositivo:

1. En el Centro de administración de Microsoft 365, vaya a **UsuariosActivosAgregue** >  >  **un usuario**.

2. Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".

4. Escriba un nombre de usuario como "MainReception" o "Mainlobby".

5. Establezca manualmente la contraseña del teléfono de área común para evitarlo. Para ello, desactive **Crear automáticamente una contraseña** y requerir que este usuario **cambie su contraseña al iniciar sesión por primera vez**.  

    >[!Important]
    > Es muy recomendable establecer una contraseña manualmente para teléfonos de área común para evitar problemas de inicio de sesión para los usuarios finales.

6. Seleccione la ubicación de uso del dispositivo y asigne el área común Teléfono licencia a la cuenta. Si se necesitan otras licencias, como Planes de llamadas, asígnelas.

>[!NOTE]
> No es necesario agregar una licencia Sistema telefónico usuario. Está incluida en la licencia del teléfono de área común.
>
>Si no está usando Teléfono Microsoft sistema de enrutamiento directo u operador Conectar, es posible que desee agregar licencias de planes de llamadas. Para obtener más información sobre licencias, [vea Microsoft Teams de complementos](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Con PowerShell

Use PowerShell cuando desee crear y asignar licencias para más de una cuenta de usuario a la vez. Vea [Crear Microsoft 365 de usuario con PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) y Asignar Microsoft 365 a cuentas de usuario [con PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) para obtener más información.

## <a name="step-3---set-policies-for-common-area-phones"></a>Paso 3: Establecer directivas para teléfonos de área común

Use directivas para controlar qué características están disponibles para los usuarios en teléfonos de área común.

>[!NOTE]
>Después de asignar una directiva, salga del teléfono e inicie sesión de nuevo. Una asignación de directiva puede tardar hasta una hora en tener efecto.

### <a name="ip-phone-policies"></a>Directivas de teléfono IP

Los teléfonos que hayan iniciado sesión con cuentas a las que se les haya asignado una licencia Teléfono área común mostrarán la experiencia de usuario del área común.

Si desea invalidar la interfaz predeterminada de un teléfono, considere la posibilidad de crear una [directiva de teléfono IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). Por ejemplo, si se usa un teléfono de área común en un área pública, establezca una directiva de teléfono IP para restringir la búsqueda en la Libreta global de direcciones de su organización y bloquear el escritorio en caliente. Vea [Establecer Teams interfaz de usuario de dispositivos Android](devices/Teams-Android-devices-user-interface.md) para obtener más información.

### <a name="calling-policies"></a>Directivas de llamada

Use directivas de llamadas para habilitar llamadas privadas, mediante el reenvío de llamadas o llamadas simultáneas en teléfonos de área común. Consulte [Llamadas y reenvío de llamadas en Teams](teams-calling-policy.md) para obtener más información.

De forma predeterminada, el parque de llamadas no está habilitado para teléfonos de área común. Tendrá que crear una directiva para habilitarla. Vea [Parque de llamadas y recuperar en Microsoft Teams](call-park-and-retrieve.md) para obtener más información.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Paso 4: Adquirir y asignar números de teléfono

Vea [Administrar números de teléfono para su organización](manage-phone-numbers-landing-page.md) para obtener información sobre cómo adquirir y asignar números de teléfono en función de la opción de conectividad RTC.

## <a name="step-5---sign-in"></a>Paso 5: iniciar sesión

Una vez que cree y configure una cuenta de usuario, puede iniciar sesión en un teléfono. Según cuántos teléfonos implemente, tiene tres opciones de inicio de sesión:

- [Inicio de sesión local](#local-sign-in)
- [Iniciar sesión desde otro dispositivo](#sign-in-from-another-device)
- [Iniciar sesión con el Centro Teams administración](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Inicio de sesión local

Para iniciar sesión localmente con un nombre de usuario y una contraseña: 

1. Activar el teléfono de área común

2. Selecciona **Iniciar sesión en este dispositivo**

3. Siga las instrucciones de inicio de sesión en el dispositivo. Una vez que haya iniciado sesión, el teléfono mostrará la experiencia de usuario del teléfono de área común.

> [!NOTE]
> Si usa una directiva de configuración personalizada que desanclar la aplicación de llamada, el teclado de marcado no aparece en el área común Teléfono. Para obtener más información sobre Teams de configuración, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Iniciar sesión desde otro dispositivo

También puede iniciar sesión en un teléfono de área común desde otro dispositivo con un código. Al iniciar sesión de esta manera, escribirá el nombre de usuario y la contraseña en otro dispositivo, en lugar de en el propio teléfono.

1. En primer lugar, en el teléfono de área común, busque el código que se muestra en la pantalla de inicio de sesión.

2. En otro dispositivo, vaya a https://www.microsoft.com/devicelogin.

3. Escriba el código y siga las instrucciones para completar el inicio de sesión.

### <a name="sign-in-using-the-teams-admin-center"></a>Iniciar sesión con el Centro Teams administración

Como administrador, puede aprovisionar e iniciar sesión de forma remota en teléfonos de área común desde el Teams de administración. Este es el método de inicio de sesión más eficaz cuando implementa un gran número de teléfonos a la vez. Vea [Aprovisionamiento remoto e inicie sesión para Teams dispositivos Android](devices/remote-provision-remote-login.md) para obtener más información.

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha configurado y iniciado sesión en teléfonos de área común para su organización, puede administrarlos en el centro Teams administración. Vea [Microsoft Teams: Administrar los dispositivos para](devices/device-management.md) obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Actualizar Microsoft Teams dispositivos de forma remota](devices/remote-update.md)
- [Administrar Microsoft Teams etiquetas de dispositivo](devices/manage-device-tags.md)
- [Microsoft Teams de estado del dispositivo](alerts/device-health-status.md)
