---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03a2501236cd8dfa708790e49719d8103a187783
ms.sourcegitcommit: 5640e8264b61c1f8cf8eb212315eeba1a794e494
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "65928833"
---
# <a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar el complemento para reunión de Microsoft Teams en Outlook

En este artículo se detallan los requisitos de autenticación y la funcionalidad del complemento Reunión Teams en Outlook para sus usuarios finales. También se muestra cómo puede habilitar reuniones privadas y ajustar la configuración de directiva para los usuarios en el modo de isla. Si tiene problemas con el complemento, consulte nuestras [instrucciones de solución de problemas más recientes](/MicrosoftTeams/troubleshoot/meetings/resolve-teams-meeting-add-in-issues).

El complemento para reunión de equipo permite a los usuarios programar reuniones de equipo desde Outlook. El complemento está disponible para Outlook en plataformas Windows, Mac, Web y móviles.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>El complemento para reunión de Microsoft Teams en Outlook para Windows

El complemento Reunión de Teams se instala automáticamente para los usuarios que tienen Microsoft Teams y Office 2013, Office 2016, Office 2019 u Office 2021 instalados en su PC Windows. Los usuarios verán el complemento reunión de Teams en la cinta de opciones Calendario de Outlook.

![Captura de pantalla del complemento reunión de Teams en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
>
>
> - No hay **ninguna URL directa** que esté vinculada al complemento de Teams.
> - Hay otras cosas que se deben tener en cuenta si en la organización se ejecutan Teams y Skype Empresarial. En determinadas circunstancias, el complemento de Teams no está disponible en Outlook. Consulte [Actualización de Skype Empresarial a Teams](upgrade-to-Teams-on-prem-tools.md) para obtener más información.
> - Los permisos de usuario para ejecutar el archivo regsvr32.exe son un requisito mínimo para el complemento de reuniones de Teams que se instalará en el equipo.
> - Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.
> - Si usa una instalación de Office Outlook de Microsoft Store, no se admite el complemento de Reuniones de Teams. Se recomienda a los usuarios que necesiten usar este complemento que instalen la versión de hacer clic y ejecutar de Office, tal como se indica en el artículo [Office en Windows 10 en modo S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).
> - Se requerirá la instalación de [Webview2](/microsoft-edge/webview2/concepts/distribution) para la característica Complemento de reunión de Teams, con las opciones de reunión incrustadas. Si WebView2 no está instalado, se redirigirá a los usuarios al explorador, lo que puede proporcionar una experiencia degradada, especialmente en el momento de la creación de la reunión.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>El complemento para reunión de Microsoft Teams en Outlook para Mac

El botón para reunión de Teams en Outlook para Mac se mostrará en la cinta de opciones de Outlook para Mac si Outlook esta ejecutando la compilación de producción 16.24.414.0 o una posterior y se activa con una suscripción de cliente de Microsoft 365 u Office 365.

La información de acceso a la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>El complemento para reunión de Microsoft Teams en Outlook Web App

El botón Reunión de equipo en Outlook Web App se mostrará en la creación del nuevo evento si el usuario se encuentra en una versión anterior de la nueva aplicación de Outlook en la Web. Consulte el [Blog de Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) para obtener información sobre cómo pueden los usuarios probar la versión anterior de la nueva aplicación de Outlook en la Web.

![Captura de pantalla del complemento reunión de Teams en Outlook Web App.](media/teams-meeting-add-in-web.png)

Las coordenadas de la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complemento de reunión de equipo en Outlook para dispositivos móviles (iOS y Android)

En la última compilación de la aplicación de Outlook para iOS y Android se muestra el botón Reunión de equipo.

![Captura de pantalla del complemento reunión de Teams en Outlook para dispositivos móviles](media/teams-meeting-add-in-mobile.png)

Las coordenadas de la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Complemento para reunión de Microsoft Teams y Buscador de disponibilidad para Outlook

Buscador de disponibilidad es un complemento para Outlook que ayuda a los usuarios de distintas empresas a llegar a un consenso sobre la hora de una reunión. Una vez que las invitaciones de reunión han proporcionado las horas preferidas, FindTime envía la invitación a la reunión en nombre del usuario. Si la opción **Reunión en línea** está seleccionada en FindTime, FindTime programará una reunión de Skype Empresarial o de Microsoft Teams. (FindTime usará el canal de reunión en línea predeterminado que su organización haya establecido).

> [!NOTE]  
> Si ha guardado una configuración de Skype Empresarial en su [panel de control de Findtime](https://findtime.microsoft.com/UserDashboard), Findtime la usará en lugar de Microsoft Teams. Si desea usar Microsoft Teams, elimine la configuración de Skype Empresarial en su panel de control.

Consulte [Programar reuniones con el Buscador de disponibilidad](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) para obtener más información.

## <a name="authentication-requirements"></a>Requisitos de autenticación

El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna. Los usuarios podrán usar el cliente de Microsoft Teams aunque no usen este método para iniciar sesión, pero no podrán programar [reuniones en línea de Microsoft Teams](https://www.microsoft.com/microsoft-teams/online-meetings) con el complemento de Outlook. Puede solucionar este inconveniente de una de las siguientes formas:

- Si la autenticación moderna no está configurada en su organización, configúrela.
- Si la autenticación moderna está configurada, pero el usuario opta por no utilizarla en el cuadro de diálogo, pídale que vuelva a iniciar sesión usando la autenticación multifactor.

Para obtener más información sobre cómo configurar la autenticación, consulte [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar las reuniones privadas

Para que se implemente el complemento, debe estar habilitado **Permitir la programación de reuniones privadas** en el Centro de administración de Microsoft Teams. En el centro de administración, vaya a **Reuniones** > **Directivas de reunión** y, en la sección **General**, habilite **Permitir la programación de reuniones privadas**).

![Captura de pantalla de la configuración en el centro de administración de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

El cliente de Microsoft Teams determina si los usuarios necesitan la versión de 32 o de 64 bits e instala el complemento correcto.

> [!NOTE]
> Es posible que los usuarios deban reiniciar Outlook después de una instalación o una actualización de Microsoft Teams para obtener el complemento más reciente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Directiva de actualización de equipos y complemento reunión de equipos para Outlook

Los clientes [pueden elegir la vía de actualización de Skype Empresarial a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Los administradores empresariales pueden usar el modo de coexistencia de Teams para definir esta vía para sus usuarios. Los administradores empresariales tienen la opción de permitir a los usuarios utilizar Teams junto con Skype Empresarial (modo Aplicaciones aisladas).

Cuando los usuarios que se encuentran en modo de Aplicaciones aisladas programan una reunión en Outlook, normalmente esperan poder decidir si se hará en Skype Empresarial o en Teams. En Outlook en la Web, Outlook para Windows y Outlook para Mac, los usuarios que se encuentran en modo de aplicaciones aisladas ven de forma predeterminada tanto el complemento de Microsoft Teams como el de Skype Empresarial. Puede establecer una configuración de directiva de reuniones de Microsoft Teams para controlar si los usuarios que se encuentran en modo de aplicaciones aisladas pueden usar solamente el complemento para reunión de Microsoft Teams o los complementos para reunión de Microsoft Teams y Skype Empresarial.

Debido a ciertas limitaciones en la versión inicial, Outlook Mobile solo puede admitir la creación de reuniones de Skype Empresarial **o** Teams. Consulte la tabla siguiente para más información.

| Modo de coexistencia en el centro de administración de Teams | Proveedor de reuniones predeterminado en Outlook para dispositivos móviles |
| --------------------------------------|---------------------------------------------|
| Aplicaciones aisladas | Skype Empresarial |
| Solo Skype Empresarial | Skype Empresarial |
| Colaboración de Skype Empresarial con Teams | Skype Empresarial |
| Colaboración y reuniones de Skype Empresarial con Teams | Teams |
| Solo Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Establecer si los usuarios que se encuentran en modo de aplicaciones aisladas pueden usar solamente el complemento para reunión de Microsoft Teams o los complementos para reunión de Microsoft Teams y Skype Empresarial

Como administrador, puede establecer una configuración de directiva de reuniones de Teams para controlar qué complemento para reunión de Outlook se usará para los *usuarios que estén en modo de aplicaciones aisladas*. Puede especificar si los usuarios que se encuentran en modo de aplicaciones aisladas pueden usar solamente el complemento para reunión de Microsoft Teams o los complementos para reunión de Microsoft Teams y Skype Empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a los usuarios que se encuentren en modo Aplicaciones aisladas y tengan el parámetro **AllowOutlookAddIn** establecido en **True** en la directiva de reuniones de Microsoft Teams. Para conocer los pasos para configurar esta directiva, consulte [Configuración de la directiva de reunión: general](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Otras consideraciones

El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:

- El complemento para reunión de Microsoft Teams requiere un buzón de Exchange para el usuario principal que programa la reunión. Asegúrese de que tiene al menos un buzón de Exchange configurado en su perfil de Outlook y úselo para programar las reuniones de Microsoft Teams con el complemento. Para obtener información sobre los requisitos de Exchange, consulte [Interacción entre Exchange y Microsoft Teams](./exchange-teams-interact.md).
- Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal. Las reuniones de canal se deben programar desde Microsoft Teams.
- El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.
- Los usuarios no pueden programar eventos en directo desde Outlook. Vaya a Teams para programar eventos en directo. Para obtener más información, vea [¿Qué son los eventos en directo de Microsoft Teams?](teams-live-events/what-are-teams-live-events.md)

Obtenga más información sobre las [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="related-topics"></a>Temas relacionados

- [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)

- [Programar una reunión de Teams desde Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
