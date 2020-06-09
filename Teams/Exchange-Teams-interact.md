---
title: Interacción entre Exchange y Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Conozca la funcionalidad que hay entre Microsoft Teams y las distintas configuraciones de Exchange, como crear equipos y unirse a ellos, crear canales y mucho más.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5debf9eb72066c90ff0af002b4e5f3b3bafe8383
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637069"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)

Para la experiencia completa de Teams, todos los usuarios deben estar habilitados para la creación de grupos de Exchange Online, SharePoint Online y Microsoft 365.

Los buzones de Exchange de los usuarios se pueden hospedar en línea o local. La integración con Exchange local requiere una implementación híbrida de Exchange. Para obtener más información acerca de la configuración de una implementación híbrida, consulte [implementaciones híbridas de Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Los usuarios alojados en Exchange online o Exchange Dedicated vNext pueden usar todas las características de Teams. Pueden crear y unirse a equipos y canales, crear y ver reuniones, llamar y conversar, modificar imágenes de Perfil de usuario (si la Directiva de buzón de Outlook en la web lo permite), y agregar y configurar conectores, fichas y bots.

Los usuarios alojados en Exchange Online Dedicated (Legacy) deben sincronizarse con Azure Active Directory en Microsoft 365 u Office 365. Pueden crear y unirse a equipos y canales, agregar y configurar pestañas y bots, y usar las características de chat y llamada. Sin embargo, no pueden modificar las imágenes de perfil, administrar reuniones, obtener acceso a los contactos de Outlook ni administrar conectores.

Los usuarios con buzones locales se deben sincronizar con Azure Active Directory. Pueden usar todas las características del escenario anterior, pero también pueden cambiar la imagen de Perfil de usuario (si la Directiva de buzón de Outlook en la web lo permite) y administrar reuniones, lo que proporciona a Exchange Server 2016 (actualización acumulativa 3) o posterior, se ejecuta localmente con OAuth configurado (preferiblemente a través del asistente de configuración híbrida de Exchange) según se describe en configurar la [autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Para habilitar la delegación de calendario para estos usuarios, también debe completar los pasos 2-3 según se describe en [configurar la integración y OAuth entre Skype empresarial online y Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); estos pasos proporcionarán a la aplicación de programación de Teams los permisos necesarios para confirmar los permisos de delegado.

La siguiente tabla proporciona una referencia rápida y útil sobre la disponibilidad de las características basadas en el entorno de Exchange.

> [!NOTE]
> La integración de características entre Exchange local y Teams requiere una implementación híbrida de Exchange. Este requisito se suma a los requisitos específicos de la versión que se llaman en algunas características de la tabla siguiente.

**Acciones compatibles:**

| El buzón del usuario se hospeda en: | eDiscovery| &nbsp;Retención legal | Policy| Administración de equipos y canales |Crear y ver reuniones en Teams| Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Obtener acceso a contactos de Outlook | Correo de voz |Agregar y configurar conectores|Agregar y configurar fichas|Agregar y configurar bots|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí |Sí |Sí<sup>8</sup>|Sí |Sí |Sí <sup>7</sup>|Sí |Sí |Sí |Sí |
|**Exchange Online Dedicated vNext**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí |Sí |Sí<sup>8</sup>|Sí |Sí |Sí <sup>7</sup>|Sí |Sí |Sí |Sí|
|**Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)|Sí <sup>2</sup>|Sí <sup>, 2, 3</sup>|Sí <sup> 4|Sí|No|No|Sí|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|Sí <sup> 5|Sí <sup> 6|Sí |Sí |
|**Exchange local** (sincronizar con la configuración de OAuth de Azure ad & es necesario)|Sí <sup>2</sup>| Sí <sup>2</sup> |Sí <sup> 4|Sí|Sí (Exchange 2016 CU3 +)|Sí<sup>8</sup> (Exchange 2016 CU3 +)|Sí |Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|Sí <sup> 5|Sí <sup> 6|Sí |Sí |

<sup>1</sup> se admite la versión Exchange 2016 CU3 y versiones posteriores.  

<sup>2</sup> las opciones de hospedaje admiten EDiscovery y retención legal para el cumplimiento de los mensajes de canal.

los mensajes de chat privado de <sup>3</sup> equipos aún no son compatibles con la retención legal de esta opción de hospedaje.

<sup>4</sup> la retención usará un buzón de sombra para que el usuario en línea almacene los mensajes. [Microsoft Teams es compatible con eDiscovery para usuarios de equipos en un entorno híbrido de Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> los usuarios de un equipo con buzón de correo de Exchange local pueden usar el buzón de voz con Teams y recibir mensajes de voz en Outlook, pero los mensajes de voz no estarán disponibles para su visualización o reproducción en el cliente de Teams.

<sup>6</sup> si uno de los propietarios de un equipo puede Agregar conectores, todos los demás miembros de ese equipo podrán hacerlo, incluso si sus buzones están alojados en local.

<sup>7</sup> solo los contactos de la carpeta contactos predeterminada. No se admite el acceso a otras carpetas o subcarpetas de contactos.

<sup>8</sup> Teams respeta la configuración de la [Directiva de buzón de correo web de Outlook](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) que está configurada por los administradores de inquilinos para controlar si los usuarios pueden cambiar su imagen de perfil. Si la opción **-SetPhotoEnabled** está desactivada en la Directiva, los usuarios no pueden agregar, modificar ni quitar su imagen de perfil. Por ejemplo, si un usuario carga una imagen de perfil aprobada por el Departamento de ti o de RRHH de su organización, no es necesario realizar ninguna acción. Sin embargo, si un usuario carga una imagen que no es apropiada, cámbiela de acuerdo con las directivas internas de la organización.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para sacar el máximo provecho de Microsoft Teams

Microsoft Teams funciona con varios servicios de Microsoft 365 y Office 365 para ofrecer a los usuarios una experiencia enriquecida. Para admitir esta experiencia, debe habilitar ciertas características o servicios y asignar licencias.

- Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online. Microsoft Teams no es compatible con SharePoint local.

- Los usuarios deben tener asignada una licencia de SharePoint Online si desean compartir archivos en chats. Si los usuarios no tienen asignada ni habilitada licencias de SharePoint Online, no tienen almacenamiento de OneDrive para la empresa en Microsoft 365 u Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la empresa en Microsoft 365 u Office 365.

- Los usuarios deben estar habilitados para la creación de grupos de Microsoft 365 para crear equipos en Microsoft Teams.

- Para permitir que Microsoft Teams funcione con Exchange local, debe configurar el nuevo protocolo de autenticación de OAuth de Exchange, preferiblemente ejecutando el Asistente de implementación híbrida de Exchange, como se describe en [configurar la autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Para permitir que los usuarios con el buzón local de Exchange programen reuniones de Teams en nombre de otro usuario, también debe completar los pasos 2-3 según se describe en [configurar integración y OAuth entre Skype empresarial online y Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

> [!NOTE]
> El complemento de equipos de Outlook se puede usar para programar una reunión de equipos para buzones hospedados en Exchange local. Sin embargo, la programación de una reunión de Teams en nombre de otro usuario con Exchange local requiere Exchange 2013 CU9 y versiones posteriores, y el nuevo protocolo de autenticación OAuth de Exchange. Tanto el delegado como el delegador deben tener un buzón en Exchange local.

> [!NOTE]
> Para la integración de Exchange local y de Teams, es necesario asignar la licencia necesaria para el usuario sincronizado de AAD.

> [!IMPORTANT]
> Si desinstala el cliente de Skype empresarial después de mover un usuario al modo **solo para equipos** , es posible que el estado de presencia deje de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Para resolver este problema, seleccione su imagen de perfil en la esquina superior derecha de Microsoft Teams y, a continuación, seleccione **configuración**. En la pestaña **General** , en **aplicación**, seleccione **registrar equipos como la aplicación de chat de Office (se debe reiniciar las aplicaciones de Office)**. Después de seleccionar esta opción, cierre y vuelva a abrir todas las aplicaciones de Office, incluido Outlook. Después de abrir Outlook, la información de presencia estará disponible.

## <a name="additional-considerations"></a>Consideraciones adicionales

A continuación se muestran algunas cosas que debe tener en cuenta al implementar Microsoft Teams en su organización.

- En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

- Controlar y proteger la configuración de directivas de cumplimiento en Teams y Exchange mediante el acceso condicional. Para obtener más información, vea [¿Cómo funcionan las directivas de acceso condicional para Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Si su organización tiene requisitos de cumplimiento para garantizar que todas las discusiones de reuniones se descubran, debe deshabilitar las reuniones privadas si el organizador tiene un buzón local de Exchange.

- En una implementación híbrida de Exchange, el contenido de los mensajes instantáneos se pueden buscar independientemente de si los participantes del chat tienen un buzón basado en la nube o un buzón local. Para obtener más información, lea [búsqueda de buzones de correo basados en la nube para usuarios locales](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para obtener información sobre la búsqueda de contenido en Teams, lea [búsqueda de contenido en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Para obtener más información sobre cómo usar Azure AD Connect para sincronizar con Azure Active Directory, consulte [integrar las identidades locales con Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>Requisitos para usuarios de buzones de Exchange local

Si los usuarios desean tener la capacidad de programar una reunión de Teams con Exchange, debe asegurarse de lo siguiente:

- Tanto el delegado como el delegador deben tener un buzón en el servidor de Exchange.

- La detección automática (automática) de la versión 2 es necesaria para permitir que el servicio de los equipos realice una detección no autenticada del buzón del usuario. La versión 2 automática es compatible con Exchange 2013 CU19 +.

- El servidor de Exchange debe estar configurado con el servidor de autenticación para EVOSTS. Se configura automáticamente como parte del asistente híbrido para Exchange (HWA).

    Si no desea ejecutar HWA, puede crear manualmente el servidor de autenticación para STS de EVO en el servidor de Exchange, siguiendo estas instrucciones para [configurar la autenticación de OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Sin embargo, le recomendamos que use el HWA.

- El servidor de Exchange debe tener una aplicación de socio configurada con un identificador de aplicación de **Skype empresarial online, 00000004-0000-0ff1-ce00-000000000000**. El servicio de programación de Teams usa el identificador y una cuenta de usuario vinculada que tiene las siguientes propiedades:

  - Oculto en la libreta de direcciones de Exchange. Es recomendable que la oculte de la libreta de direcciones porque es una cuenta de usuario deshabilitada.

  - Asignación de roles de administración de Exchange de **UserApplication**.

Para completar la integración, siga los pasos 1-3 de la configuración de la [autenticación de OAuth entre las organizaciones locales de Exchange y Exchange Online?](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations) Tenga en cuenta que el paso 2 incluye asignación de roles para ArchiveApplication que no es necesaria para la delegación, pero que es para archivar SfB online chat en un buzón de Exchange.
