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
ms.openlocfilehash: 6d908373cf3e8df6429823d9245cf53a52fbf901
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796544"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), Grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la Empresa: [Conceptos básicos de Microsoft Teams](https://aka.ms/teams-foundations)

Para disfrutar de la experiencia completa de Teams, debe habilitarse a los usuarios en Exchange Online, SharePoint Online y la creación de Grupos de Microsoft 365.

Los buzones de correo de Exchange se pueden hospedar en línea o en el entorno local.

Los usuarios hospedados en Exchange Online o en vNext dedicado de Exchange pueden utilizar todas las características de Teams. Pueden crear y conectar equipos y canales, crear y ver reuniones, llamar y chatear, modificar imágenes de perfil de usuario (si la directiva de buzón de correo de Outlook en la Web se lo permite) y agregar y configurar conectores, pestañas y bots. Para obtener una lista más exhaustiva de las características disponibles, consulte la siguiente tabla.

Los usuarios hospedados en Exchange Online dedicado (heredado) deben estar sincronizados en Azure Active Directory en Microsoft 365 u Office 365. Pueden crear equipos y canales y unirse a ellos, agregar y configurar fichas y bots y utilizar las características de chat y llamada. Sin embargo, no pueden modificar imágenes de perfil, administrar reuniones, acceder a contactos de Outlook o administrar conectores.

> [!IMPORTANT]
> Para la integración en el entorno local, se recomienda encarecidamente tener una implementación completa de Exchange Classic Hybrid con Exchange Server 2016 o posterior. La compatibilidad con Modern Hybrid se limita a Libre/Ocupado y no ofrecerá integración del calendario desde Teams a buzones de correo en el entorno local, por ejemplo. Para más información sobre la configuración de una implementación híbrida, consulte [Implementaciones híbridas de Exchange Server](/exchange/exchange-hybrid).

Los usuarios con buzones de correo hospedados en el entorno local deben estar sincronizados con Azure Active Directory. Pueden utilizar todas las características en el escenario descrito anteriormente. Además, pueden administrar reuniones si se cumplen los requisitos enumerados en la sección [Requisitos para buzones de correo hospedados en el entorno local](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

La siguiente tabla ofrece una referencia rápida y útil de la disponibilidad de las características según el entorno de Exchange.

**Acciones compatibles:**

| El buzón del usuario se hospeda en:                                        | eDiscovery       | Legal&nbsp;Hold    | Retención  | Administración de equipos y canales | Crear y ver reuniones en Teams | Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Acceder a contactos de Outlook | Correo de voz  | Agregar y configurar conectores | Agregar y configurar fichas | Agregar y configurar bots |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Sí<sup>1</sup> | Sí <sup>1</sup>   | Sí        | Sí                   | Sí                               | Sí<sup>7</sup>             | Sí          | Sí             | Sí<sup>6</sup>        | Sí        | Sí                          | Sí                    | Sí                    |
| **Exchange Online Dedicated vNext**                                 | Sí<sup>1</sup> | Sí <sup>1</sup>   | Sí        | Sí                   | Sí                               | Sí<sup>7</sup>             | Sí          | Sí             | Sí<sup>6</sup>        | Sí        | Sí                          | Sí                    | Sí                    |
| **Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)  | Sí<sup>1</sup> | Sí<sup>1,2</sup> | Sí<sup>3</sup> | Sí                   | No                                | No                          | Sí          | Sí             | No                      | Sí <sup>4</sup> | Sí<sup>5</sup>                   | Sí                    | Sí                    |
| **Exchange local** (Sincronizar con Azure AD) | Sí <sup>1,9</sup> | Sí<sup>1</sup>   | Sí<sup>3</sup> | Sí                   | Sí<sup>8</sup>         | Sí                          | Sí          | Sí             | No                      | Sí <sup>4</sup> | Sí<sup>5</sup>                   | Sí                    | Sí                    |

<sup>1</sup> eDiscovery y la suspensión legal para el cumplimiento en los mensajes de canal se admiten en todas las opciones de hospedaje.

<sup>2</sup> Los mensajes de chat privado de Teams todavía no se admiten para la Suspensión legal en esta opción de hospedaje.

<sup>3</sup> La retención empleará un buzón de correo sombra para que el usuario en línea almacene mensajes.

<sup>4</sup> Los usuarios de Teams con buzón de correo de Exchange en el entorno local pueden usar el buzón de voz con Teams y recibir mensajes del buzón de voz en Outlook, pero los mensajes del buzón de voz no estarán disponibles para ver o reproducir dentro del cliente de Teams.

<sup>5</sup> Si uno de los propietarios de un equipo puede agregar conectores, los demás miembros del equipo también podrán, incluso si sus buzones de correo están hospedados en el entorno local.

<sup>6</sup> Solo los contactos en la carpeta predeterminada de contactos. No se admite el acceso a otras carpetas o subcarpetas de contactos.

<sup>7</sup> Teams respeta la configuración de la [directiva de buzón de Outlook en la Web](/powershell/module/exchange/client-access/set-owamailboxpolicy) que está configurada por los administradores de espacios empresariales para controlar si los usuarios pueden cambiar su imagen de perfil. Si la configuración **-SetPhotoEnabled** está desactivada en la directiva, los usuarios no pueden agregar, cambiar o quitar su imagen de perfil, por lo que la imagen de porfile no se sincronizará con los equipos si el administrador cambia la foto.

<sup>8</sup> Deberá cumplir los requisitos enumerados en la sección [Requisitos para crear y ver reuniones para buzones de correo hospedados en el entorno local](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

<sup>9</sup> También se requiere un mínimo Exchange Online licencia del Plan 1. Para obtener más información, vea [Buscar Teams de chat para usuarios locales.](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para sacar el máximo provecho de Microsoft Teams

Microsoft Teams trabaja con varios servicios de Microsoft 365 y Office 365 para ofrecer a los usuarios una experiencia enriquecedora. Para admitir esta experiencia, deberá habilitar ciertas características o servicios y asignar licencias.

- Se debe asignar una licencia de Exchange Online a los usuarios.

- Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online. Microsoft Teams no admite SharePoint local.

- Se debe asignar una licencia de SharePoint Online a los usuarios para que puedan compartir archivos en Chats. Si a los usuarios no se les asigna ni se les habilita licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365 o en Microsoft 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en Chats si no disponen de almacenamiento de OneDrive para la Empresa en Office 365 o en Microsoft 365.

- Es necesario habilitar a los usuarios para que puedan crear grupos de Microsoft 365 y así poder crear equipos en Microsoft Teams.

  > [!IMPORTANT]
  > Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, puede que la presencia deje de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Para resolver este problema, seleccione su imagen de perfil en la esquina superior derecha de Microsoft Teams y, a continuación, seleccione **Configuración**. En la pestaña **General** en **Aplicación**, seleccione **Registrar Teams como la aplicación de chat para Office (requiere reiniciar las aplicaciones de Office)**. Tras seleccionar esta opción, cierre y vuelva a abrir todas las aplicaciones de Office, incluido Outlook. Tras abrir Outlook, estará disponible la información de presencia.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Requisitos para crear y ver reuniones para buzones de correo hospedados en el entorno local.

Si los buzones de correo están hospedados en el entorno local, se deben cumplir los siguientes requisitos para poder crear y ver reuniones:

- Se debe asignar la licencia requerida de Teams al usuario sincronizado de Azure Active Directory.

- Los usuarios deben estar sincronizados con Azure Active Directory. Para más información sobre cómo usar Azure AD Connect para la sincronización con Azure Active Directory, consulte [Documentación de la identidad híbrida](/azure/active-directory/hybrid/).

- Los buzones de correo están hospedados en la actualización acumulativa 3 o posterior de Exchange Server 2016.

- Los Servicios de detección automática y de Web Exchange se publican externamente.

- La autenticación OAuth se configura preferiblemente mediante la ejecución de una configuración híbrida completa (Clásica o Moderna) realizada por el Asistente para configuración de Exchange Hybrid. Si no puede utilizar el Asistente para configuración de Hybrid, configure OAuth como se describe en [Configurar la autenticación OAuth entre organizaciones de Exchange y de Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  > [!NOTE]
  > Exchange confía en el Token de OAuth del servicio de Teams, conocido como EvoSTS. El paso 1 debería bastar, peroe solo EvoSTS; ACS se emplea para la búsqueda Libre/Ocupado en el calendario.

- Está establecida la casilla de verificación para la característica de la implementación híbrida de Exchange en Azure AD Connect. Para obtener más información, [vea Exchange escritura híbrida.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback)

- Para la compatibilidad con la aplicación de calendario y el complemento de Outlook Teams para Mac, las direcciones URL del Servicio web Exchange se deben configurar como SPN en el espacio empresarial de Azure AD para la entidad de servicio de Exchange. Este paso se puede realizar con el Asistente para configuración de Hybrid o mediante los [pasos del manual para la Autenticación moderna híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Para habilitar la delegación del calendario para estos usuarios:

- También debe completar los pasos descritos en Configurar integración [y OAuth entre Skype Empresarial Online y Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); estos pasos proporcionarán a la Teams programación los permisos necesarios para confirmar los permisos delegados.
 
  > [!NOTE]
  > El paso 2 incluye la asignación de rol para ArchiveApplication, lo que no se requiere para la delegación.

- El Teams programación de Outlook para Exchange 2013 CU19 o posterior al programar una reunión en nombre de otra persona. Se requiere para admitir la detección no autenticada del buzón de correo por parte de nuestro servicio para contrastar los permisos delegados con el buzón de correo de la persona que delega. La ubicación del delegado y de la persona que delega puede ser Exchange 2013 o posterior, o Exchange Online, pero la Detección automática debe resolver a Exchange 2013 CU19 o posterior.

## <a name="additional-considerations"></a>Consideraciones adicionales

He aquí algunas consideraciones adicionales para la implementación de Microsoft Teams en su organización.

- En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

- Controlar y proteger la configuración de directivas de cumplimiento en Teams y Exchange mediante el Acceso condicional. Para más información, consulte [¿Cómo funcionan las directivas de Acceso condicional en Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange. Para más información, consulte [Permitir la programación de reuniones privadas](./meeting-policies-in-teams-general.md#allow-scheduling-private-meetings).

- En una implementación híbrida de Exchange, el contenido de los mensajes de chat se puede buscar sin importar que los participantes del chat tengan un buzón de correo basado en la nube o local. Para más información, consulte [Búsqueda de buzones basados en la nube para usuarios locales](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para más información sobre la búsqueda de contenido en Teams, consulte [Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Para el estado de presencia, Microsoft Teams debe comprobar si el buzón de correo está hospedado en Exchange Online o en el entorno local. Entonces, el servicio decide dónde acceder al buzón de correo. Para habilitar el servicio de Teams para comprobar la ubicación del buzón de correo mediante la llamada de la REST API al servicio de Exchange Online, debe implementar un entorno híbrido de Exchange mediante el asistente para configuración híbrida de Exchange, como se describe en [Crear una implementación híbrida con el asistente para configuración híbrida](/exchange/hybrid-deployment/deploy-hybrid).

## <a name="troubleshooting"></a>Solución de problemas

Para obtener una guía completa de solución de problemas sobre este tema, consulte [Solucionar problemas de interacción entre Microsoft Teams y Exchange Server](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
