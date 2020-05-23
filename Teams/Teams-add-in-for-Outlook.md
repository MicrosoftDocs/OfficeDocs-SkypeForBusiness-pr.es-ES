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
ms.openlocfilehash: 89e7db133b8878e77dbf14025b97c658b0de21e4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349614"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar el complemento para reunión de Microsoft Teams en Outlook
=======================================

El complemento para reunión de equipo permite a los usuarios programar reuniones de equipo desde Outlook. El complemento está disponible para Outlook en plataformas Windows, Mac, Web y móviles.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>El complemento para reunión de Microsoft Teams en Outlook para Windows

El complemento de reunión de Teams se instala automáticamente para los usuarios que tienen Microsoft Teams y Office 2013, Office 2016 u Office 2019 instalado en su PC con Windows. Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook.

![Captura de pantalla del complemento de reunión de equipo en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Existen otras consideraciones adicionales si su organización ejecuta tanto equipos como Skype empresarial. En algunas circunstancias, el complemento de Teams no está disponible en Outlook. Para obtener más información, consulte [actualizar de Skype empresarial a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Los permisos de usuario para ejecutar el archivo regsvr32.exe son un requisito mínimo para el complemento de reuniones de Teams que se instalará en el equipo.
> - Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.
> - Si usa una instalación de Office Outlook de Microsoft Store, no se admite el complemento de Reuniones de Teams. Se recomienda a los usuarios que necesiten usar este complemento que instalen la versión de hacer clic y ejecutar de Office, tal como se indica en el artículo [Office en Windows 10 en modo S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>El complemento para reunión de Microsoft Teams en Outlook para Mac

El botón reunión de equipos de Outlook para Mac aparecerá en la cinta de opciones de Outlook para Mac si Outlook está ejecutando la compilación de producción 16.24.414.0 y versiones posteriores, y se activa con una suscripción de cliente de Microsoft 365 u Office 365.

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
FindTime es un complemento para Outlook que ayuda a los usuarios a alcanzar consenso en una reunión en todas las empresas. Una vez que las invitaciones de reunión han proporcionado las horas preferidas, FindTime envía la invitación a la reunión en nombre del usuario. Si la opción **Reunión en línea**está seleccionada en FindTime, FindTime programará una reunión de Skype Empresarial o de Microsoft Teams. (FindTime usará el canal de reunión en línea predeterminado que su organización haya establecido).

> [!NOTE]  
> Si ha guardado una configuración de Skype Empresarial en su [panel de control de Findtime](https://findtime.microsoft.com/UserDashboard), Findtime la usará en lugar de Microsoft Teams. Si desea usar Microsoft Teams, elimine la configuración de Skype Empresarial en su panel de control.

Para obtener más información, consulte [programar reuniones con FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

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
| Colaboración y reuniones de Skype Empresarial con Teams | Equipos |
| Solo Teams | Teams |

## <a name="other-considerations"></a>Otras consideraciones

El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:

- Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal. Las reuniones de canal se deben programar desde Microsoft Teams.
- El complemento no funcionará si un proxy de autenticación se encuentra en la ruta de acceso de red de los servicios de equipo y equipo del usuario.
- Los usuarios no pueden programar eventos en directo desde Outlook. Vaya a Teams para programar eventos en directo. Para obtener más información, vea [¿Qué son los eventos en directo de Microsoft Teams?](teams-live-events/what-are-teams-live-events.md)

Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Solución de problemas

Realice los pasos siguientes para solucionar problemas con el complemento de reunión de Teams.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>El complemento de reunión de Teams en Outlook para Windows no se muestra

Si no consigue instalar el complemento Reunión de Teams para Outlook, pruebe estos pasos para solucionarlo.

- Los usuarios de Windows 7 deben instalar la [Actualización Universal C Runtime en Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que el complemento Reunión de Teams funcione.
- Compruebe que el usuario tiene una directiva de actualización de teams que permite programar reuniones en Teams. Para obtener más información, consulte [actualizar de Skype empresarial a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
- Compruebe que el usuario tiene una directiva de reunión de teams que permite el complemento de Outlook. Para obtener más información, vea [Administrar directivas de reunión en Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) .
- Asegúrese de que el usuario tiene instalado el cliente de escritorio de Teams. El complemento de reunión no se instalará cuando solo se use el cliente web de Teams.
- Asegúrese de que el usuario tiene instalado Outlook 2013 o una versión posterior.
- Asegúrese de que el usuario tiene permiso para ejecutar regsvr32. exe.
- Asegúrese de que se hayan aplicado todas las actualizaciones disponibles para el cliente de escritorio de Outlook.
- Siga estos pasos:
  - Reinicie el cliente de escritorio de Teams.
  - Cierre la sesión y vuelva a iniciarla en el cliente de escritorio de Teams.
  - Reinicie el cliente de escritorio de Outlook. (Asegúrese de que Outlook no se esté ejecutando en el modo de administración).

Si sigue sin ver el complemento, asegúrese de que no está deshabilitado en Outlook.

- En Outlook, elija **archivo** y, a continuación, **Opciones**.
- Seleccione la pestaña **Complementos** del cuadro de diálogo **Opciones de Outlook** .
- Confirme que el **complemento de reunión de Microsoft Teams para Microsoft Office** aparece en la lista **Complementos de aplicaciones activas**
- Si el complemento de reunión de Teams aparece en la lista **Complementos de aplicaciones deshabilitada** , seleccione **Complementos com** en **administrar** y, después, seleccione **ir...**
- Active la casilla que se encuentra junto al **complemento de reuniones de Microsoft Teams para Microsoft Office**.
- Elija **Aceptar** en todos los cuadros de diálogo y reinicie Outlook.

Para obtener instrucciones generales sobre cómo administrar los complementos, vea [ver, administrar e instalar complementos en los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Si el complemento sigue sin mostrarse, siga estos pasos para comprobar la configuración del registro.

> [!NOTE]
> La edición incorrecta del registro puede dañar gravemente el sistema. Antes de realizar cambios en el registro, debe hacer una copia de seguridad de los datos valiosos del equipo.
- Iniciar regedit. exe
- Ir a HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins
- Verifique que TeamsAddin. FastConnect exista.
- Dentro de TeamsAddin. FastConnect, compruebe que LoadBehavior exista y esté establecido en 3.
  - Si LoadBehavior tiene un valor distinto de 3, cámbielo a 3 y reinicie Outlook.

### <a name="delegate-scheduling-does-not-work"></a>La programación delegada no funciona

Si el administrador ha configurado Microsoft Exchange para [controlar el acceso al servidor Web de Exchange (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), el delegado no podrá programar una reunión de Teams en nombre del jefe. La solución para esta configuración está en desarrollo y se publicará en el futuro. 
