---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26eb3af88b6e16de0535d25d4b5205a72626b7b2
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521536"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar el complemento para reunión de Microsoft Teams en Outlook
=======================================

El complemento para reunión de equipo permite a los usuarios programar reuniones de equipo desde Outlook. El complemento está disponible para Outlook en plataformas Windows, Mac, Web y móviles.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>El complemento para reunión de Microsoft Teams en Outlook para Windows

El complemento para reunión de Microsoft Teams se instala automáticamente para los usuarios que tienen instalado Microsoft Teams y Office 2010, Office 2013 u Office 2016 en su equipo Windows. Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook.

![Captura de pantalla del complemento de reunión de equipo en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Existen otras consideraciones adicionales si su organización ejecuta tanto equipos como Skype empresarial. En algunas circunstancias, el complemento de Teams no está disponible en Outlook. Para obtener más información, consulte [actualizar de Skype empresarial a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Los permisos de usuario para ejecutar el archivo regsvr32.exe son un requisito mínimo para el complemento de reuniones de Teams que se instalará en el equipo.
> - Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.
> - Si usa una instalación de Office Outlook de Microsoft Store, no se admite el complemento de Reuniones de Teams. Se recomienda a los usuarios que necesiten usar este complemento que instalen la versión de hacer clic y ejecutar de Office, tal como se indica en el artículo [Office en Windows 10 en modo S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>El complemento para reunión de Microsoft Teams en Outlook para Mac

El botón Reunión de equipos se mostrará en la cinta de opciones de Outlook para Mac si Outlook está ejecutando la compilación de producción 16.24.414.0 o posterior y se activa con una suscripción de cliente de Office 365.

La información de acceso a la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>El complemento para reunión de Microsoft Teams en Outlook Web App

El botón Reunión de equipo en Outlook Web App se mostrará en la creación del nuevo evento si el usuario se encuentra en una versión anterior de la nueva aplicación de Outlook en la Web. Consulte el [Blog de Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) para obtener información sobre cómo pueden los usuarios probar la versión anterior de la nueva aplicación de Outlook en la Web.

![Captura de pantalla del complemento de reunión de equipo en Outlook Web App](media/teams-meeting-add-in-web.png)

Las coordenadas de la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complemento de reunión de equipo en Outlook para dispositivos móviles (iOS y Android)

En la última compilación de la aplicación de Outlook para iOS y Android se muestra el botón Reunión de equipo.

![Captura de pantalla del complemento de reunión de equipo en Outlook para dispositivos móviles](media/teams-meeting-add-in-mobile.png)

Las coordenadas de la reunión (el enlace para unirse a Teams y los números de acceso telefónico) se añadirán a la invitación a la reunión cuando el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Complemento de reunión de equipos en FindTime para Outlook
FindTime es un complemento para Outlook que ayuda a los usuarios a alcanzar consenso acerca de la hora de una reunión entre distintas empresas. Una vez que las invitaciones de reunión han proporcionado las horas preferidas, FindTime envía la invitación a la reunión en nombre del usuario. Si la opción **Reunión en línea**está seleccionada en FindTime, FindTime programará una reunión de Skype Empresarial o de Microsoft Teams. (FindTime usará el canal de reunión en línea predeterminado que su organización haya establecido).

> [!NOTE]  
> Si ha guardado una configuración de Skype Empresarial en su [panel de control de Findtime](https://findtime.microsoft.com/UserDashboard), Findtime la usará en lugar de Microsoft Teams. Si desea usar Microsoft Teams, elimine la configuración de Skype Empresarial en su panel de control.

Consulte [Programar reuniones con FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) para obtener más información.

## <a name="authentication-requirements"></a>Requisitos de autenticación

El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna. Si los usuarios no usan este método para iniciar sesión, aún podrán usar el cliente de Teams, pero no podrán programar reuniones en línea de Teams mediante el complemento de Outlook. Puede solucionar este inconveniente de una de las siguientes formas:

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

Cuando los usuarios que se encuentran en modo de Aplicaciones aisladas programan una reunión en Outlook, normalmente esperan poder decidir si se hará en Skype Empresarial o en Teams. En Outlook en la Web, Outlook para Windows y Outlook para Mac, los usuarios que se encuentran en modo de Aplicaciones aisladas ven Skype Empresarial y Teams como complementos. Debido a algunas limitaciones de la versión inicial, Outlook para dispositivos móviles solo admite la creación de reuniones de Skype Empresarial **o** de Teams. Consulte la siguiente tabla para obtener información.

| Modo de coexistencia en el centro de administración de Teams | Proveedor de reuniones predeterminado en Outlook para dispositivos móviles |
| --------------------------------------|---------------------------------------------|
| Aplicaciones aisladas | Skype Empresarial |
| Solo Skype Empresarial | Skype Empresarial |
| Colaboración de Skype Empresarial con Teams | Skype Empresarial |
| Colaboración y reuniones de Skype Empresarial con Teams | Teams |
| Solo Teams | Teams |

## <a name="other-considerations"></a>Otras consideraciones

El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:

- Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal. Las reuniones de canal se deben programar desde Microsoft Teams.
- El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.
- Los usuarios no pueden programar eventos en directo desde Outlook. Vaya a Teams para programar eventos en directo. Para obtener más información, vea [¿Qué son los eventos en directo de Microsoft Teams?](teams-live-events/what-are-teams-live-events.md)

## <a name="troubleshooting"></a>Solución de problemas

Si no consigue instalar el complemento Reunión de Teams para Outlook, pruebe estos pasos para solucionarlo.

- Asegúrese de que se han aplicado todas las actualizaciones disponibles para el cliente de escritorio de Outlook.
- Reinicie el cliente de escritorio de Teams.
- Cierre la sesión y vuelva a iniciarla en el cliente de escritorio de Teams.
- Reinicie el cliente de escritorio de Outlook. (Asegúrese de que Outlook no se esté ejecutando en el modo de administración).
- Asegúrese de que el nombre de la cuenta de usuario activa no contiene espacios. (Este es un problema conocido y se corregirá en una actualización futura).
- Asegúrese de que el inicio de sesión único (SSO) está habilitado.

Si el administrador ha configurado Microsoft Exchange para [controlar el acceso al servidor Web de Exchange (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), el delegado no podrá programar una reunión de Teams en nombre del jefe. La solución para esta configuración está en desarrollo y se publicará en el futuro. 

Para obtener instrucciones generales sobre cómo desactivar complementos, consulte [Ver, administrar e instalar los complementos de los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
