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
ms.openlocfilehash: 35c020d981fba9827f10753a04b9b5629a9939df
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177210"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)

Para la experiencia completa de Teams, todos los usuarios deben estar habilitados para la creación de grupos de Exchange Online, SharePoint Online y Microsoft 365.

Los buzones de Exchange de los usuarios se pueden hospedar en línea o local.

Los usuarios alojados en Exchange online o Exchange Dedicated vNext pueden usar todas las características de Teams. Pueden crear y unirse a equipos y canales, crear y ver reuniones, llamar y conversar, modificar imágenes de Perfil de usuario (si la Directiva de buzón de Outlook en la web lo permite), y agregar y configurar conectores, fichas y bots. Para obtener una lista más completa de las características disponibles, consulte la tabla siguiente.

Los usuarios alojados en Exchange Online Dedicated (Legacy) deben sincronizarse con Azure Active Directory en Microsoft 365 u Office 365. Pueden crear y unirse a equipos y canales, agregar y configurar pestañas y bots, y usar las características de chat y llamada. Sin embargo, no pueden modificar las imágenes de perfil, administrar reuniones, obtener acceso a los contactos de Outlook ni administrar conectores.

> [!IMPORTANT]
> Para la integración en local, se recomienda encarecidamente tener una implementación híbrida completa de Exchange completa con Exchange Server 2016 o posterior. La compatibilidad con entornos híbridos modernos está limitada a disponibilidad y no proporcionará integración de calendarios de equipos a buzones de correo locales, por ejemplo. Para obtener más información acerca de la configuración de una implementación híbrida, consulte [implementaciones híbridas de Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Los usuarios con buzones locales se deben sincronizar con Azure Active Directory. Pueden usar todas las características del escenario anterior, pero además, pueden administrar reuniones si se cumplen los requisitos [de los buzones hospedados en](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) la sección local.

La siguiente tabla proporciona una referencia rápida y útil sobre la disponibilidad de las características basadas en el entorno de Exchange.

**Acciones compatibles:**

| El buzón del usuario se hospeda en:                                        | eDiscovery       | &nbsp;Retención legal    | Policy  | Administración de equipos y canales | Crear y ver reuniones en Teams | Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Obtener acceso a contactos de Outlook | Correo de voz  | Agregar y configurar conectores | Agregar y configurar fichas | Agregar y configurar bots |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Sí <sup>1</sup> | Sí <sup>1</sup>   | Sí        | Sí                   | Sí                               | Sí<sup>7</sup>             | Sí          | Sí             | Sí <sup>6</sup>        | Sí        | Sí                          | Sí                    | Sí                    |
| **Exchange Online Dedicated vNext**                                 | Sí <sup>1</sup> | Sí <sup>1</sup>   | Sí        | Sí                   | Sí                               | Sí<sup>7</sup>             | Sí          | Sí             | Sí <sup>6</sup>        | Sí        | Sí                          | Sí                    | Sí                    |
| **Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)  | Sí <sup>1</sup> | Sí <sup>, 1, 2</sup> | Sí <sup> 3 | Sí                   | No                                | No                          | Sí          | Sí             | No                      | Sí <sup> 4 | Sí <sup> 5                   | Sí                    | Sí                    |
| **Exchange local** (sincronizar con Azure ad) | Sí <sup>1</sup> | Sí <sup>1</sup>   | Sí <sup>3</sup> | Sí                   | Sí <sup>8</sup>         | No                          | Sí          | Sí             | No                      | Sí <sup> 4 | Sí <sup> 5                   | Sí                    | Sí                    |

<sup>1</sup> las opciones de hospedaje admiten EDiscovery y retención legal para el cumplimiento de los mensajes de canal.

los mensajes de chat privado de <sup>2</sup> equipos aún no son compatibles con la retención legal de esta opción de hospedaje.

<sup>3</sup> la retención usará un buzón de sombra para que el usuario en línea almacene los mensajes.

<sup>4</sup> los usuarios de equipos de Exchange pueden usar el buzón de voz con Teams y recibir mensajes de voz en Outlook, pero los mensajes de voz no estarán disponibles para su visualización o reproducción en el cliente de Teams.

<sup>5</sup> si uno de los propietarios de un equipo puede Agregar conectores, todos los demás miembros de ese equipo podrán hacerlo, incluso si sus buzones están alojados en local.

<sup>6</sup> solo los contactos de la carpeta contactos predeterminada. No se admite el acceso a otras carpetas o subcarpetas de contactos.

<sup>7</sup> Teams respeta la configuración de la [Directiva de buzón de correo web de Outlook](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) que está configurada por los administradores de inquilinos para controlar si los usuarios pueden cambiar su imagen de perfil. Si la opción **-SetPhotoEnabled** está desactivada en la Directiva, los usuarios no pueden agregar, modificar ni quitar su imagen de perfil. Por ejemplo, si un usuario carga una imagen de perfil aprobada por el Departamento de ti o de RRHH de su organización, no es necesario realizar ninguna acción. Sin embargo, si un usuario carga una imagen inadecuada, cámbiela de acuerdo con las directivas internas de la organización.

<sup>8</sup> necesita cumplir los requisitos enumerados en los [requisitos para crear y ver las reuniones de los buzones hospedados en una sección local](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) .

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para sacar el máximo provecho de Microsoft Teams

Microsoft Teams funciona con varios servicios de Microsoft 365 y Office 365 para ofrecer a los usuarios una experiencia enriquecida. Para admitir esta experiencia, debe habilitar ciertas características o servicios y asignar licencias.

- Los usuarios deben tener asignada una licencia de Exchange Online.

- Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online. Microsoft Teams no es compatible con SharePoint local.

- Los usuarios deben tener asignada una licencia de SharePoint Online si desean compartir archivos en chats. Si los usuarios no tienen asignada ni habilitada licencias de SharePoint Online, no tienen almacenamiento de OneDrive para la empresa en Microsoft 365 u Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la empresa en Microsoft 365 u Office 365.

- Los usuarios deben estar habilitados para la creación de grupos de Microsoft 365 para crear equipos en Microsoft Teams.

> [!IMPORTANT]
> Si desinstala el cliente de Skype empresarial después de mover un usuario al modo **solo para equipos** , es posible que el estado de presencia deje de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Para resolver este problema, seleccione su imagen de perfil en la esquina superior derecha de Microsoft Teams y, a continuación, seleccione **configuración**. En la pestaña **General** , en **aplicación**, seleccione **registrar equipos como la aplicación de chat de Office (se debe reiniciar las aplicaciones de Office)**. Después de seleccionar esta opción, cierre y vuelva a abrir todas las aplicaciones de Office, incluido Outlook. Después de abrir Outlook, la información de presencia estará disponible.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Requisitos para crear y ver reuniones de buzones de correo hospedados localmente

Si los buzones son locales, para crear y ver reuniones, deben cumplirse los siguientes requisitos:

- Es necesario asignar la licencia de Teams requerida para el usuario sincronizado de Azure Active Directory.

- Los usuarios deben estar sincronizados con Azure Active Directory. Para obtener más información sobre cómo usar Azure AD Connect para sincronizar con Azure Active Directory, consulte la documentación de la [identidad híbrida](https://docs.microsoft.com/azure/active-directory/hybrid/).

- Los buzones se hospedan en la actualización acumulativa 3 de Exchange Server 2016 o una versión posterior.

- Detección automática y los servicios Web de Exchange se publican externamente.

- La autenticación de OAuth se configura preferiblemente mediante el Asistente de configuración híbrida de Exchange que ejecuta una configuración híbrida completa (clásica o moderna). Si no puede usar el Asistente para la configuración híbrida, configure OAuth como se describe en [configurar la autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

 > [!NOTE]
 > El token de OAuth de Exchange confía del servicio de Teams, que se conoce como EvoSTS. El paso 1 debe ser suficiente, pero solo el EvoSTS; ACS se usa para la búsqueda de disponibilidad en el calendario.

- Se establece la casilla de verificación de la característica implementación híbrida de Exchange en Azure AD Connect.

- Para el soporte técnico de la aplicación de calendario y el complemento de Outlook para Mac, las direcciones URL del servicio Web de Exchange deben configurarse como SPN en Azure AD de inquilino para la entidad de servicio de Exchange. Este paso se realiza con el Asistente para la configuración híbrida o siguiendo [los pasos manuales de la autenticación moderna híbrida](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Para habilitar la delegación de calendario para estos usuarios:

- También debe completar los pasos 2-3 según se describe en [configurar integración y OAuth entre Skype empresarial online y Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); estos pasos proporcionarán a la aplicación de programación de Teams los permisos necesarios para confirmar los permisos de delegado.
 
 > [!NOTE]
 > El paso 2 incluye asignación de roles para ArchiveApplication, que no es necesario para la delegación.

- Complemento de programación de Teams para Outlook cuando se programa una reunión en nombre de alguien, se requiere Exchange 2013 CU19 o una versión posterior. Esto es compatible con el descubrimiento no autenticado del buzón de correo por nuestro servicio para comprobar los permisos de delegado con el buzón delegador. La ubicación de delegación y delegador podría ser Exchange 2013 o posterior, o Exchange Online, pero la detección automática debe resolverse en Exchange 2013 CU19 o posterior.

## <a name="additional-considerations"></a>Consideraciones adicionales

A continuación se muestran algunas cosas que debe tener en cuenta al implementar Microsoft Teams en su organización.

- En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

- Controlar y proteger la configuración de directivas de cumplimiento en Teams y Exchange mediante el acceso condicional. Para obtener más información, vea [¿Cómo funcionan las directivas de acceso condicional para Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Si su organización tiene requisitos de cumplimiento para garantizar que todas las discusiones de reuniones se descubran, debe deshabilitar las reuniones privadas si el organizador tiene un buzón local de Exchange. Para obtener más información, consulte [permitir la programación de reuniones privadas](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- En una implementación híbrida de Exchange, el contenido de los mensajes instantáneos se pueden buscar independientemente de si los participantes del chat tienen un buzón basado en la nube o un buzón local. Para obtener más información, lea [búsqueda de buzones de correo basados en la nube para usuarios locales](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para obtener información sobre la búsqueda de contenido en Teams, lea [búsqueda de contenido en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

## <a name="troubleshooting"></a>Solución de problemas

Para obtener una guía de solución de problemas completa sobre el tema, asegúrese de consultar solucionar problemas de [interacción con Microsoft Teams y Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
