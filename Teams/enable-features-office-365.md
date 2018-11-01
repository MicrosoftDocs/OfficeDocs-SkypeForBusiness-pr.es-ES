---
title: Administrar las características de Microsoft Teams en su organización de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Obtenga información sobre cómo activar o desactivar las aplicaciones de Microsoft Teams en su organización de Office 365, incluidas las fichas, conectores, bots o cualquier combinación de los tres.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7411494c3baa56c1761ee3bcd69c2d49fdd4a961
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890567"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Administrar las características de Microsoft Teams en su organización de Office 365

Todas las opciones de los equipos pronto se van a migrar a la nueva Microsoft Teams & Skype para el centro de administración de negocio. La única característica de los equipos que se administra en el centro de administración de Office 365 es las aplicaciones. 

A menos que se indique lo contrario, es el valor predeterminado para una opción **en**.

## <a name="office-365-tenant-wide-settings"></a>Configuración a nivel de inquilino de Office 365 

En **configuración de todo el inquilino**, puede activar o desactivar aplicaciones.

Para editar el **inquilino de toda la configuración** de los equipos, vaya a la Teams Microsoft & Skype para el centro de administración de negocio y seleccione **portal heredado**. Después, elija **Configuración** > **Servicios y complementos** > **Microsoft Teams**. Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Aplicaciones

Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos que proporciona un servicio de terceros. Hay directivas de administración de Microsoft Teams que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas. Estas directivas le permiten especificar qué aplicaciones están permitidos y no permitidos, nuevo comportamiento de la aplicación externa, y si se permite la carga de lado aplicaciones. 

La sección **Aplicaciones** le permite establecer la siguiente configuración para su organización: 

![Captura de pantalla de la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Permitir aplicaciones externas en Microsoft Teams:** si este conmutador está activado, los usuarios pueden agregar las fichas y los bots que estén disponibles al inquilino de Office 365. 
 
    ![Captura de pantalla del control para permitir aplicaciones externas en la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Habilitar nuevas aplicaciones externas de manera predeterminada**: si este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams. Desactive este conmutador si quiere controlar las aplicaciones nuevas. Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés. 

- **Permitir sideloading de aplicaciones externas**: cuando este modificador está activado, los usuarios pueden instalar y activar bots personalizados y fichas. 

Para obtener más información, consulte [Configurar la administración para aplicaciones en Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Configuración de toda la organización de los equipos

Puede controlar la configuración del usuario de toda la organización en Microsoft Teams & Skype para el centro de administración de negocio. Para editar la configuración de toda la organización, vaya a la Skype Microsoft para el centro de administración de negocio y, a continuación, seleccione **configuración de toda la organización**. Puede configurar los valores siguientes.

### <a name="external-access"></a>Acceso externo

**Acceso externo** permite a los equipos y Skype para los usuarios empresariales comunicarse con los usuarios que están fuera de su organización. Para configurar el acceso externo, vaya a [Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Acceso de invitado

**Acceso de invitado** en Microsoft Teams permite a los equipos de la organización para colaborar con personas fuera de su organización mediante la concesión de acceso a los equipos y los canales. Cualquier usuario con una cuenta de correo electrónico empresariales o de clientes, como Outlook, Gmail u otras personas, puede participar como invitado en los equipos con acceso total al equipo chats, reuniones y archivos. Para obtener más información, vea [acceso como invitado en los equipos de Microsoft](guest-access.md).

### <a name="teams-settings"></a>Configuración de los equipos

En **configuración de los equipos**, puede configurar la integración del correo electrónico, opciones de almacenamiento en la nube, Skype para la interoperabilidad de negocio y los dispositivos.

#### <a name="email-integration"></a>Integración del correo electrónico

Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar mensajes de correo electrónico a cualquier canal en un equipo que tenga que agregar conectores activan para los miembros del equipo. Para activar la integración del correo electrónico, asegúrese de que es **Permitir a los usuarios enviar mensajes de correo electrónico a una dirección de correo electrónico de canal** **en**. 

#### <a name="files"></a>Archivos

Aquí puede activar o desactivar la opción opciones de almacenamiento de archivo de la nube y uso compartido de archivo. 

Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Microsoft Teams. Opciones de almacenamiento en la nube en los equipos de incluyen actualmente ShareFile, lista desplegable, cuadro y la unidad de Google. Active el conmutador de los proveedores de almacenamiento en nube que quiera usar su organización.

#### <a name="organization"></a>Organización

Aquí puede activar en la ficha **organización** , que se muestra el gráfico de organización detallado para la organización del usuario. Para obtener más información, vea [uso de la ficha organización en los equipos](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="skype-for-business-interop"></a>Skype para la interoperabilidad de negocio

Use esta opción para permitir que el chat de los usuarios de los equipos con Skype para los usuarios empresariales. Para obtener información detallada acerca de la interoperabilidad entre los equipos y Skype para la empresa, vaya a [comprender los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="devices"></a>Dispositivos

Esta configuración controla el comportamiento de la cuenta de recursos para dispositivos concentradores de superficie para asistir a reuniones de Microsoft Teams. Use estas opciones para configurar los requisitos de autenticación, requieren un PIN de contenido y activar las cuentas de recursos de concentrador de superficie para enviar mensajes.

- ANCLAR **requieren una forma secundaria de autenticación para tener acceso a contenido de la reunión** – seleccionar el nivel de acceso que tienen los usuarios cuando entran en el contenido.
- **Establecer contenido PIN** – requieren que los usuarios escriban este PIN para impedir el acceso no autorizado a los documentos. Esto evita que un usuario no autorizado unirse a reuniones próximas y exploración de datos adjuntos.
- **Las cuentas de recursos pueden enviar mensajes** – activar esta opción **en** para permitir que los mensajes que se envíen desde la cuenta del recurso concentrador de superficie.

#### <a name="search"></a>Buscar.

Búsqueda en el directorio con ámbito Teams Microsoft usa directiva de la libreta de direcciones de Exchange (APB) para permitir que las organizaciones a crear límites virtuales ese control cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización. Es posible que desee utilizar una búsqueda en directorios con ámbito en situaciones como las siguientes:

- Su organización tiene varias empresas dentro de su inquilino que desea mantener separados. 
- Su escuela desea limitar chats entre profesores y estudiantes. 

Cambiar esta configuración **en** para activar las búsquedas de directorio con ámbito.

### <a name="teams-upgrade"></a>Actualización de los equipos

Puede usar estas opciones para configurar cómo se actualizarán los usuarios de Skype para la empresa a Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistencia
Se puede especificar un modo de coexistencia: **sólo los equipos**, **Islas** (equipos y Skype para realizarán empresarial coexistir) o **Skype para la empresa sólo**. El modo de coexistencia que elija determina el enrutamiento de llamadas entrantes y chats y la aplicación que se utilizó el usuario para iniciar charlas y las llamadas o para programar reuniones. Para obtener más información acerca de los modos de coexistencia, vaya a [comprender los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferencias de aplicación

Aquí puede elegir la aplicación que los usuarios utilizarán para unirse a Skype para la empresa las reuniones (Skype para empresariales o de la [Aplicación de las reuniones de Skype](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Esta opción no depende de la configuración del modo de coexistencia.

## <a name="how-can-i-tell-which-features-are-available"></a>¿Cómo puedo saber qué características están disponibles?

Vea la [Guía básica de Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para obtener información acerca de las nuevas características de los equipos. Para obtener más información acerca de las características nuevas y futuras, consulte la página equipos [What ' s New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) y el [blog de equipos de la Comunidad de Microsoft Tech](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) para los equipos. 
