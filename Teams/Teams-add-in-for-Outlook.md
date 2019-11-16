---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89f9ba68dd4fbd1cef271c0dd0a3fb73e10637a7
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38626986"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar el complemento para reunión de Microsoft Teams en Outlook
=======================================

El complemento de reunión de Teams permite a los usuarios programar una reunión de Teams desde Outlook. El complemento está disponible para Outlook en Windows, Mac, Web y móvil.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Complemento de reunión de Teams en Outlook para Windows

El complemento de reunión de Teams se instala automáticamente para los usuarios que tengan Microsoft Teams y Office 2010, Office 2013 u Office 2016 instalado en su PC con Windows. Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook.

![Captura de pantalla del complemento de reunión de Teams en la cinta de Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Los permisos de usuario para ejecutar el archivo regsvr32. exe son un requisito mínimo para el complemento de reuniones de teams que se instalará en el equipo.
> - Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.
> - Los usuarios de Windows 7 deben instalar la [actualización de tiempo de ejecución de C universal en Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que funcione el complemento de reunión de equipos.
> - Si está usando una instalación de Office Outlook desde Microsoft Store, no se admite el complemento de reunión de Teams. Se recomienda a los usuarios que necesiten este complemento instalar la versión de hacer clic y ejecutar de Office, tal como se indica en el artículo [modo de Office en Windows 10 en modo S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) .


## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Complemento de reunión de Teams en Outlook para Mac

El botón reunión de equipos de Outlook para Mac aparecerá en la cinta de opciones de Outlook para Mac si Outlook está ejecutando la compilación de producción 16.24.414.0 y versiones posteriores.

Las coordenadas de la reunión (el vínculo de la unión entre equipos y los números de acceso telefónico) se agregarán a la invitación a la reunión después de que el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Complemento de reuniones de Teams en Outlook Web App

El botón reuniones de Teams de Outlook Web App aparecerá como parte de la creación de nuevos eventos si el usuario se encuentra en una versión anterior de la nueva versión de Outlook en la Web. Vea el [blog de Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) para obtener información sobre cómo los usuarios pueden probar la versión anterior de la nueva versión de Outlook en la Web.

![Captura de pantalla del complemento de reunión de Teams en Outlook Web App](media/teams-meeting-add-in-web.png)

Las coordenadas de la reunión (el vínculo de la unión entre equipos y los números de acceso telefónico) se agregarán a la invitación a la reunión después de que el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complemento de reunión de Teams en Outlook Mobile (iOS y Android)

El botón reunión de equipos se muestra en las versiones más recientes de la aplicación Outlook para iOS y Android.

![Captura de pantalla del complemento de reunión de Teams en Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Las coordenadas de la reunión (el vínculo de la unión entre equipos y los números de acceso telefónico) se agregarán a la invitación a la reunión después de que el usuario haga clic en **Enviar**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Complemento de reunión de Teams y FindTime para Outlook
FindTime es un complemento para Outlook que ayuda a los usuarios a alcanzar un consenso en las reuniones de las empresas. Una vez que los invitados de la reunión han proporcionado sus horas preferidas, FindTime envía la invitación a la reunión en nombre del usuario. Si la opción **reunión en línea** está seleccionada en FindTime, FindTime programará una reunión de Skype empresarial o de Microsoft Teams. (FindTime usará la que su organización haya establecido como canal predeterminado de reuniones en línea).

> [!NOTE]  
> Si guardó una configuración de Skype empresarial en el [Panel de Findtime](https://findtime.microsoft.com/UserDashboard), Findtime la usará en lugar de Microsoft Teams. Si desea usar Microsoft Teams, elimine la configuración de Skype empresarial en el panel.

Para obtener más información, vea [programar reuniones con FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) .

## <a name="authentication-requirements"></a>Requisitos de autenticación

El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna. Aunque los usuarios no usen este método para iniciar sesión, podrán usar el cliente de Microsoft Teams, pero no podrán programar reuniones en línea de Microsoft Teams usando el complemento de Outlook. Puede solucionar este inconveniente de una de las siguientes formas:

- Si la autenticación moderna no está configurada en su organización, configúrela.
- Si la autenticación moderna está configurada pero cancelada en el cuadro de diálogo, debe indicar a los usuarios que inicien sesión de nuevo con la autenticación multifactor.

Para obtener más información sobre cómo configurar la autenticación, consulte [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar las reuniones privadas

**Permitir la programación de reuniones privadas** debe estar habilitado en el centro de administración de Microsoft Teams para que se implemente el complemento. En el centro de administración, vaya a **Reuniones** > **Directivas de reunión** y, en la sección **General**, habilite **Permitir la programación de reuniones privadas**).

![Captura de pantalla de la configuración en el centro de administración de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

El cliente de Microsoft Teams determina si los usuarios necesitan la versión de 32 o de 64 bits e instala el complemento correcto.

> [!NOTE]
> Es posible que los usuarios deban reiniciar Outlook después de una instalación o una actualización de Microsoft Teams para obtener el complemento más reciente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Directiva de actualización de Teams y complemento de reuniones de Teams para Outlook

Los clientes pueden [elegir el viaje de actualización de Skype empresarial a teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Los administradores de inquilinos pueden usar el modo de coexistencia de equipos para definir este viaje para sus usuarios. Los administradores de inquilinos tienen la opción de permitir que los usuarios usen Teams junto con Skype empresarial (modo Islas). 

Cuando los usuarios que están en modo de isla programan una reunión en Outlook, generalmente esperan poder elegir si desean programar una reunión de Skype empresarial o de Teams. En Outlook en la web, Outlook Windows y Outlook Mac, los usuarios ven los complementos de Skype empresarial y de equipos en el modo islas. Debido a determinadas limitaciones en la versión inicial, Outlook Mobile solo puede admitir la creación de reuniones de Skype empresarial **o** de Teams. Para obtener más información, consulta la tabla siguiente.

| Modo de coexistencia en el centro de administración de Teams | Proveedor de reuniones predeterminado en Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Logra | Skype Empresarial |
| Solo Skype Empresarial | Skype Empresarial |
| Skype empresarial con colaboración de Teams | Skype Empresarial |
| Skype empresarial con colaboración y reuniones de Teams | Teams |
| Solo Teams | Teams |

## <a name="other-considerations"></a>Otras consideraciones

El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:

- Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal. Las reuniones de canal se deben programar desde Microsoft Teams.
- El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.
- Los usuarios no pueden programar eventos en vivo desde Outlook. Vaya a Teams para programar eventos en vivo. Para obtener más información, vea [¿Qué son los eventos de Microsoft Teams Live?](teams-live-events/what-are-teams-live-events.md).

## <a name="troubleshooting"></a>Solución de problemas

Si no consigue instalar el complemento Reunión de Teams para Outlook, pruebe estos pasos para solucionarlo.

- Asegúrese de que se hayan aplicado todas las actualizaciones disponibles para el cliente de escritorio de Outlook.
- Reinicie el cliente de escritorio de Teams.
- Cierre la sesión y vuelva a iniciarla en el cliente de escritorio de Teams.
- Reinicie el cliente de escritorio de Outlook. (Asegúrese de que Outlook no se está ejecutando en modo de administrador).
- Asegúrese de que el nombre de la cuenta de usuario activa no contiene espacios. (Este es un problema conocido y se corregirá en una actualización futura).
- Asegúrese de que el inicio de sesión único (SSO) está habilitado.

Si el administrador ha configurado Microsoft Exchange para [controlar el acceso al servidor Web de Exchange (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un delegado no podrá programar una reunión de Teams en nombre del jefe. La solución para esta configuración está en desarrollo y se publicará en el futuro. 

Para obtener instrucciones generales sobre cómo desactivar complementos, consulte [Ver, administrar e instalar los complementos de los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
