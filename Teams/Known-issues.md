---
title: Problemas conocidos de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 2/25/2019
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: marcl
localization_priority: Priority
search.appverid: MET150
description: Lista actual de problemas conocidos en la aplicación cliente de Microsoft Teams y en la experiencia de los administradores.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 377d86bd71947588186979f20068b9e8927ccd3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287913"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conocidos de Microsoft Teams

En este artículo se indican los problemas conocidos de Microsoft Teams por área de características.

## <a name="administration"></a>Administración

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|    
|:-----|:-----|:-----|:-----|
|Departamento de cuentas de recursos mal configuradas  <br/> |Las cuentas de recursos asociadas con una cola de llamada u operador automático creadas antes de enero de 2019 puede que no tengan el parámetro del departamento configurado correctamente, lo que podría provocar una asignación errónea de números de teléfono. Se está realizando una corrección para resolver este problema. <br/> |Para mitigar este problema, puede ejecutar el siguiente Cmdlet para configurar el parámetro de departamento. Set-MsolUser -ObjectId <Resource Account Object ID> : Department "Microsoft Communication Application Instance" <br/> |8/5/19 <br/> |




|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los registros de auditoría pueden notificar un nombre de usuario incorrecto como iniciador cuando se ha eliminado a alguien de un equipo  <br/> |El equipo de Microsoft Teams es un grupo moderno en AAD. Cuando se agregan o se quitan miembros mediante la interfaz de usuario de Teams, el flujo sabe exactamente quién fue el usuario que inició el cambio y el registro de auditoría refleja la información correcta. Sin embargo, si un usuario agrega o quita un miembro mediante AAD, el cambio se sincroniza en el backend de Microsoft Teams sin informar a Teams acerca de quién inició la acción. Microsoft Teams considera que el primer propietario del equipo es el iniciador, lo que se verá finalmente reflejado en el registro de auditoría.    <br/> |  <br/> |11/05/2018  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La directiva de EAF del Kit de herramientas de Experiencia de mitigación mejorada (EMET) puede identificar incorrectamente las optimizaciones del espacio aislado de Chromium como amenazas. <br/> |Hay un problema con el espacio aislado de Chromium en el que la directiva de exportación del filtrado de acceso a la tabla de direcciones (EAF) del Kit de herramientas de Experiencia de mitigación mejorada (EMET) y de la Protección contra amenazas avanzada (ATP) de Windows Defender puede identificar incorrectamente las optimizaciones del espacio aislado de Chromium como amenazas. Esto hace que Teams no funcione correctamente.  <br/> | Para solucionar este problema, desactive EAF en Microsoft Teams. Puede leer más información sobre el problema [Directrices de mitigaciones de EMET](https://support.microsoft.com/es-ES/help/2909257/emet-mitigations-guidelines). Para obtener más información acerca de la directiva de ATP y EAF de Windows Defender, vea [Personalizar la protección contra las vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection) <br/> |11/10/2018 <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden agregar miembros a los equipos cuando UsersPermissionToReadOtherUsersEnabled está establecido como falso  <br/> |Cuando este valor se establece como falso en AAD, el cliente no puede agregar miembros externos o internos en Microsoft Teams, y aparece el siguiente mensaje de error: "No se han podido agregar los miembros. Ha surgido un problema. Inténtelo de nuevo más tarde". Sin embargo, los miembros se pueden agregar directamente en los grupos de Office 365.    <br/> |En AAD, cambie este ajuste a verdadero.  <br/> |10/4/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La administración de conectores a nivel de inquilino ya no está disponible  <br/> |Al intentar agregar un conector en la versión de cliente y la versión en línea, se recibe el error: Se ha producido un error inesperado. Inténtalo de nuevo. Set-OrganizationConfig -ConnectorsEnabled=True   <br/> |Deshabilítelo en la configuración de Microsoft Teams. Vea este artículo de soporte: https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21/6/17  <br/> |

## <a name="apps"></a>Aplicaciones

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que [Acceso condicional](https://docs.microsoft.com/es-ES/azure/active-directory/conditional-access/overview) no funcione cuando use la pestaña "Sitio Web" en la aplicación de escritorio<br/> |Si un sitio web, por ejemplo, un portal de intranet, cuenta con directivas de acceso condicional (como restricciones en el explorador o las direcciones IP), ese sitio web puede no parecer como una pestaña dentro de Teams en la aplicación de escritorio <br/> |Usar Teams en un explorador en lugar de en la aplicación de escritorio.  <br/> |1/7/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Faltan opciones de conector para algunos equipos  <br/> |Cuando se hace clic con el botón derecho en un canal, la opción Conectores no aparece para ningún miembro del equipo.  <br/> |El usuario que cree el equipo debe tener un buzón en línea; de lo contrario, la opción Conector no estará disponible. Este es el comportamiento que se espera.  <br/> |26/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La aplicación "Tareas" permanece visible cuando se deshabilita  <br/> |Cuando se deshabilita la aplicación "Tareas" en el centro de administración, permanece visible en el cliente de Teams para los usuarios con licencia EDU. Si se selecciona cuando está deshabilitada, aparece el mensaje de error: "¡Vaya! Ha habido un problema..."  <br/> |No hay ninguna solución.  <br/> |29/12/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden eliminar los conectores como propietario de un equipo  <br/> |Al intentar eliminar un conector como propietario, (que sí puede agregar un conector), mientras está deshabilitada la opción "Permitir a los miembros crear, actualizar y quitar conectores", aparece un error que indica que el usuario no tiene permiso para hacerlo. <br/> |Si se habilita temporalmente "Permitir a los miembros crear, actualizar y quitar conectores", el propietario podrá eliminar el conector.  <br/> |27/07/2018  <br/> |

## <a name="audio-conferencing"></a>Audioconferencia

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los autores de llamadas RTC con el mismo número "Desde" aparecen como el mismo usuario en la lista de la reunión.  <br/> |Cuando varios autores de llamadas RTC se unen a una reunión y sus identificadores de llamada se enmascaran como un solo número, se mostrarán como un único llamador en la lista de la reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|El panel de información de la reunión no aparece intermitentemente.  <br/> |Es posible que el panel de información de la reunión no se muestre en el cliente de Microsoft Teams cuando los usuarios intentan buscar números de teléfono de puente de conferencia o id. de conferencia.  <br/> |Busque en los detalles de la reunión o en el calendario de Outlook los números de teléfono de puente de conferencia o los id. de conferencia.  <br/> |25/9/2017  <br/> |
|Las invitaciones a reuniones desde el complemento de Outlook muestran como caracteres dañados en las coordenadas RTC para las configuraciones regionales de fuera de EE. UU.  <br/> |Al programar reuniones privadas con el complemento de Outlook para Microsoft Teams en un equipo sin configuraciones regionales de fuera de EE. UU., las coordenadas RTC podrían tener caracteres dañados.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Las llamadas externas deben usar 5 dígitos o más.  <br/> |Los usuarios que intentan realizar llamadas externas desde una reunión deberán marcar 5 o más dígitos, aunque haya disponible una regla normativa de plan de marcado para normalizar la marcación de dígitos breve a E.164.  <br/> |Realice las llamadas externas escribiendo el número DID completo o el formato de número local en vez del número de extensión interna.  <br/> |25/9/2017  <br/> |
|El control de llamadas externas no aparece intermitentemente.  <br/> |Es posible que el control de llamadas externas no esté visible desde el panel de información de la reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|No se admite el id. de conferencia estático para las reuniones de Microsoft Teams.  <br/> |Si el administrador reemplaza la configuración predeterminada de id. de conferencia dinámico a id. de conferencia estático, este ajuste no tendrá vigor en las reuniones de Microsoft Teams. Vea [Uso de identificadores dinámicos de Audioconferencia en su organización](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Las coordenadas de RTC no están disponibles para los usuarios locales de Skype Empresarial  <br/> |Si el usuario es un usuario local de Skype Empresarial que tiene asignadas licencias de Skype Empresarial Online, Audioconferencia y Microsoft Teams, las reuniones programadas con Teams no incluirán coordenadas de reuniones de RTC. <br/> |No hay ninguna solución.  <br/> |01/02/2018  <br/> |

## <a name="authentication"></a>Autenticación

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando intenta unirse a Teams desde Internet Explorer o Edge, el programa lo intenta constantemente o se bloquea y no consigue iniciar sesión.   <br/> | Su organización utiliza los sitios de confianza de Internet Explorer y la aplicación basada en web de Teams no logra iniciar sesión correctamente porque los sitios de confianza de Teams no están permitidos. <br/>|Haga los siguientes cambios en la configuración de IE o desde el Panel de control, ya sea con derechos de administrador o con un objeto de directiva de grupo:<br/><ol><li>En **Opciones de Internet** &gt; **Privacidad** &gt; **Avanzada**, acepte las cookies de origen y de terceros, y active la casilla **Aceptar siempre las cookies de sesión**.</li><li>Haga clic en **Opciones de Internet** &gt; **Seguridad** &gt; **Sitios de confianza** &gt; **Sitios** y agregue lo siguiente:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>NOTA</b>: Valide y permita siempre todas las direcciones URL de confianza de Teams y los requisitos del siguiente documento: [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Limitaciones de complementos de Outlook  <br/> |Para usar el complemento de Outlook, debe iniciar sesión en Microsoft Teams con la autenticación multifactor. Si se produce un error en la autenticación multifactor durante el proceso de inicio de sesión, podrá iniciar sesión en Microsoft Teams, pero recibirá un mensaje de error cuando intente usar el complemento.  <br/> Por el momento, el complemento solo está disponible para los usuarios de Windows.  <br/> El complemento no funcionará si usa un proxy de autenticación.  <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams siempre iniciará sesión en la cuenta de PC unida a un dominio.   <br/> |Si un usuario tiene dos cuentas diferentes de Microsoft Teams y tiene un equipo con la opción de unido a dominio habilitada, Teams usará el perfil unido a un dominio en el equipo para iniciar sesión automáticamente en Teams. Para cambiar a la otra cuenta de Teams, el usuario deberá cerrar la sesión de la aplicación manualmente y especificar las credenciales de la segunda cuenta para iniciar sesión. Si el usuario cierra la sesión de Teams y reinicia el equipo, después de reiniciar, Teams iniciará sesión automáticamente con el perfil unido a dominio. <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Error de autenticación moderna: autenticación de Forms no habilitada  <br/> |Cuando se produce un error inicial en la autenticación multifactor, use la aplicación web para la autenticación.  <br/> Para obtener más información, consulte [Servicios de federación de Active Directory prompt=login parameter support](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Compruebe esta configuración: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Planner en compilación de inicio de sesión único (SSO) <br/> |El inicio de sesión único no se aplica en Planner. Tendrá que volver a iniciar sesión la primera vez que use Planner en cada cliente.  <br/> |No hay ninguna solución. Estamos trabajando en otras mejoras para la autenticación.  <br/> |28/02/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede guardar la imagen de perfil  <br/> |Los usuarios no pueden guardar su imagen de perfil cuando el buzón de Exchange está hospedado (alojado) localmente en Exchange 2016 CU2 o anterior.  <br/> |No hay ninguna solución.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Explorador

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Aparecen anomalías verdes cuando se presenta un vídeo en Chrome.  <br/> |Aparecen anomalías verdes cuando se ve un vídeo o se comparte la pantalla en una llamada o una reunión en Chrome.  <br/> |Deshabilite la configuración de aceleración de hardware en Chrome.  <br/> |03/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Compatibilidad con el cliente web de Safari  <br/> | Teams ahora está disponible en versión preliminar en Safari 11.1 + en macOS. Durante la versión preliminar, los usuarios pueden encontrarse problemas relacionados con la prevención de seguimiento inteligente de Safari [Problemas conocidos de Safari](https://go.microsoft.com/fwlink/?linkid=2062082).  <br/> | Mientras la compatibilidad del explorador Safari está en versión preliminar, vaya a **Preferencias > Privacidad**  y desactive la opción  **Evitar seguimiento entre sitios**  . A continuación, cierre el explorador y vuelva a teams.microsoft.com en Safari. <br/> |02/11/2016  <br/> |


## <a name="channels"></a>Canales

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando un usuario abandona la compañía, aparece en Microsoft Teams como "Usuario desconocido"<br/> |Cuando un usuario abandona la compañía, aparece en Microsoft Teams como "Usuario desconocido". Además, la ficha de conversaciones muestra: "Se ha agregado a Usuario desconocido al equipo". <br/> |No hay ninguna solución.  <br/> |12/09/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden volver a crear un nombre de canal que haya existido anteriormente.  <br/> |Una vez que se crea el nombre de un canal, este no se puede volver a usar, incluso si se ha eliminado. Nuestro sistema mantiene estos datos para posibles situaciones de protección de información.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cambiar el nombre de un canal en Microsoft Teams no cambia el nombre de la carpeta correspondiente en SharePoint Online  <br/> |Si cambia el nombre de un canal en Microsoft Teams, la carpeta en la biblioteca de documentos de SharePoint Online correspondiente al equipo no cambia la coincidencia. El nombre de carpeta correcto de SharePoint Online se muestra en la parte superior de la ficha Archivos del canal que ha cambiado el nombre.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La vista previa de direcciones URL podría no mostrarse para todas las URL  <br/> |Es posible que algunas direcciones URL no se muestren en una vista previa.  Esto depende de su la URL original tiene la capacidad de mostrar una vista previa. <br/> |No hay ninguna solución. <br/> |01/09/2018 <br/> |

## <a name="chat"></a>Chat

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|@menciones de notificaciones de envío de mensajes eliminados con vínculo al canal  <br/> |Hay una limitación de notificaciones conocida cuando se recibe una @mención en un mensaje que se ha eliminado; la notificación de la fuente navegará al canal, pero no a un mensaje específico. <br/> | Deliberado <br/> | 28/03/2017  <br/>|


## <a name="client"></a>Cliente

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams no actualiza automáticamente   <br/> | Cuando Microsoft Teams se instala en Archivos de programa mediante scripts de instalación en vez de la ubicación predeterminada, el cliente no actualiza automáticamente cuando aparecen nuevas versiones.    <br/> | Deliberado. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El vínculo simbólico o la asignación de una unidad a C:\users hace que la aplicación se inicie en una pantalla blanca  <br/> | Cuando Microsoft Teams se instala en Archivos de programa mediante scripts de instalación en vez de la ubicación predeterminada, el cliente no actualiza automáticamente cuando aparecen nuevas versiones.   <br/> | Deliberado. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`. Si la asignación es necesaria, deberá usar la versión web de Microsoft Teams.  <br/> | 07/09/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El vínculo simbólico o la asignación de una unidad a C:\users hace que la aplicación se inicie en una pantalla blanca  <br/> |Cuando la ubicación predeterminada de `C:\users\<user>\appData` cambia al mover la carpeta `C:\users` o al usar el vínculo simbólico, la aplicación se iniciará en una pantalla blanca.   <br/> |No hay ninguna solución alternativa conocida. Si la asignación es necesaria, deberá usar la versión web de Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Entorno

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los buzones de grupo no están habilitados para poder archivar en ellos (almacenamiento extra).  <br/> |En el Centro de seguridad y cumplimiento de Office 365, los administradores globales no pueden habilitar el archivado en los buzones de grupo. Solo pueden hacerlo en los buzones de los usuarios.  <br/> |Si la capacidad del buzón de grupo está casi llena, póngase en contacto con el soporte técnico de Microsoft Office para ampliar el tamaño del buzón.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Acceso de invitados

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los clientes de la UE y APAC reciben un error cuando agregan un usuario invitado desde otro inquilino    <br/> | Los clientes de la UE y APAC sufren un retraso en la replicación entre Microsoft Teams y Azure Active Directory. Cuando un usuario de un inquilino de UE o APAC intenta agregar un usuario invitado desde otro inquilino, recibe un mensaje de error indicando que vuelva a intentarlo.   <br/> |Haga clic en el botón para reintentar y vuelva a realizar la adición del usuario invitado.  <br/> |08/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se ha creado una wiki para los canales que creen los invitados.  <br/> |Cuando un invitado crea un canal, no se crea la ficha **Wiki**. La ficha **Wiki** no se puede adjuntar manualmente al canal. <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

## <a name="meetings"></a>Reuniones

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden acceder a las reuniones o conectores, pero tienen buzones de Exchange Online. <br/> |El cliente bloquea activamente EWS de los servicios de Exchange Online, pero necesita tener Microsoft Teams en cumplimiento de las directivas de EWS. <br/> |Para que MS Teams cumpla con la normativa, debe agregar las siguientes cadenas de agente de usuario para MS Teams en EWSAllowList: `SkypeSpaces/*` y `MicrosoftNinja/*`, incluidos los asteriscos. Se puede usar el siguiente comando: `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Para obtener más información: https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps. <br/> |30/05/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se necesita Skype Empresarial para algunas reuniones.  <br/> |Para su comodidad, su calendario de citas se muestra en Microsoft Teams. Para entrar en una reunión, solo tiene que hacer clic en el botón **Unirse**. <br/> Mientras trabajamos para seguir desarrollando esta área, si esta reunión se programó con Skype Empresarial, cuando haga clic en **Unirse**, Microsoft Teams iniciará su cliente de Skype Empresarial para que pueda terminar de entrar en la reunión. Las reuniones que se programaron en Microsoft Teams se iniciarán directamente en este producto.  <br/> En el futuro, simplificaremos esta experiencia.  <br/> |Haga clic en **Unirse**. Microsoft Teams decidirá de manera inteligente si es necesario Skype Empresarial para que un usuario se una a la reunión en función de la dirección URL que se ha incluido en la descripción de la reunión.  <br/> |13/03/2017  <br/> |


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Número máximo de asistentes para las reuniones  <br/> |Cada reunión de Microsoft Teams puede albergar un máximo de 250 asistentes.  <br/> |Cree eventos en directo en equipos que puedan albergar 10 000 usuarios.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Reuniones no disponibles  <br/> |La funcionalidad de reuniones no está disponible cuando Exchange Mailbox está hospedado (alojado) localmente en versiones inferiores a Exchange 2016 CU3.  <br/> |Actualice a la actualización acumulada 3 de Exchange 2016 o posterior para la implementación local.  <br/> |28/02/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No hay audio mientras se comparte contenido durante una reunión de difusión  <br/> |Al compartir el contenido durante una reunión de difusión, los participantes no pueden oír el audio del contenido compartido (vínculo de youtube o archivo de vídeo guardado).  <br/> |Ninguna, ya que se ha diseñado así.  Teams actualmente no admite audio del contenido compartido  <br/> |09/10/2018  <br/> |

## <a name="mobile"></a>Móvil

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden ver los canales marcados como favoritos automáticamente  <br/> |Algunos miembros no pueden ver los canales marcados como favoritos automáticamente en la aplicación móvil.  <br/> |Los miembros deben iniciar sesión primero en la aplicación de escritorio o en la aplicación web para ver los canales marcados como favoritos automáticamente en sus aplicaciones móviles.  <br/> |30/04/2018  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El selector de cosas divertidas, los Giphys o los adhesivos no se pueden usar en la aplicación móvil  <br/> |No se pueden usar archivos GIF, emojis o adhesivos en los clientes móviles.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Diferencias de diseño del cliente móvil de Microsoft Teams  <br/> |Los equipos se muestran en una lista ordenada alfabéticamente y los canales no se pueden contraer en el cliente móvil.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|


## <a name="people"></a>Personas

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Fotos de perfiles de usuario  <br/> | Actualmente, Teams no tiene un mecanismo para impedir que los usuarios cambien la foto. El equipo de BTS se ha reunido con el equipo de desarrollo que ha registrado el siguiente tema para su consideración: Característica 108874: Directiva de TI para deshabilitar la carga de fotos de perfil   <br/> | Si tiene clientes que desean tener la posibilidad de impedir la carga de fotos de perfilen Teams, avíseles que pueden agregar su voto y su caso de negocio en los comentarios: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |

## <a name="provisioning"></a>Aprovisionamiento

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se ha creado un usuario de SharePoint incorrecto para el sitio de SharePoint en Microsoft Teams.  <br/> |El administrador de SharePoint aparece como el creador de SharePoint para un grupo de Microsoft Teams, en lugar del usuario correcto.  <br/> Cuando se realiza una auditoría desde la consola de administración de SharePoint, el creador de la página de colección de sitios asociada con el grupo de Office 365 que se crea con el equipo de Microsoft Teams es el administrador de SharePoint.  <br/> |No hay ninguna solución.  <br/> |21/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden crear un equipo.  <br/> |Es posible que su empresa haya establecido una directiva para restringir quién puede crear equipos o grupos de Office 365.  <br/> |Compruébelo con su administrador de TI para saber cuál es la directiva de su empresa en relación con la creación de grupos y equipos.  <br/> |13/03/2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Actualización de Skype Empresarial a Microsoft Teams

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Pestañas

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La ficha Sitio web provoca la confusión de los clientes  <br/> |Las fichas Sitio web no son equivalentes a las de su explorador. Una serie de sitios, en especial los que requieren autenticación o el uso de ventanas emergentes, no funcionarán cuando se anclan como ficha de sitio web.  <br/> |Estamos trabajando en mejorar la interfaz de usuario para que sea más obvia para los clientes.  <br/> |02/05/2018  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las fichas no funcionan desde que se habilitó el acceso condicional <br/> |Es posible que algunas fichas no se carguen más en el cliente de escritorio desde que se habilitó el Acceso condicional en el inquilino. Las fichas se cargan cuando se usa el cliente web. Algunas de las fichas que se pueden ver afectadas son: PowerBI, Forms, VSTS, PowerApps y SharePoint List.  <br/> |Para ver las fichas afectadas, deberá usar Microsoft Teams en Microsoft Edge, IE o Chrome con la extensión de cuentas de Windows 10 instalada. Algunas fichas todavía dependen de la autenticación web, que no funciona en el cliente de escritorio cuando la entidad de certificación está habilitada. Estamos trabajando con nuestros socios para habilitar estos escenarios; de momento hemos habilitado Planner, OneNote y Stream. <br/> |05/04/2018  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de espacios de trabajo no está ordenada alfabéticamente.  <br/> |Los usuarios que tienen que cambiar de espacio de trabajo cuando agregan una ficha PowerBI verán que la lista de espacios de trabajo entre los que tienen que alternar no está ordenada alfabéticamente.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La barra de desplazamiento desaparece cuando se seleccionan informes.  <br/> |Cuando los usuarios que agregan informes de PowerBI intentan desplazarse por una lista que es más extensa que la pantalla de los informes no pueden evitar que se pierda la barra de desplazamiento.  <br/> |Use la flecha arriba o la flecha abajo para desplazarse por la lista.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Integración de Teams Planner con Planner Online <br/> |Los cubos de tareas de Planner no se muestran en la experiencia de Planner Online.  <br/> |No hay ninguna solución. <br/> |28/02/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Ficha OneNote heredada  <br/> |Las fichas OneNote heredadas que se crearon durante la versión preliminar pública de Microsoft Teams no se pueden eliminar ni se les puede cambiar el nombre.  <br/> |No hay ninguna solución. <br/> |8/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Función de búsqueda en la pestaña de lista de SharePoint  <br/> |Si se intenta abrir un archivo desde la función de búsqueda de la pestaña de lista de SharePoint, aparecerá un aviso "Necesitará una nueva aplicación para abrir este archivo" y el archivo no se abrirá. <br/> |Abra directamente desde la lista en lugar de la barra de búsqueda. <br/> |11/2/2019  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Error de descarga de archivos <br/> |Intentar descargar un archivo cuando la ruta del archivo contiene un apóstrofo desencadenará un error "El archivo no se ha descargado" al usar al cliente de escritorio de Microsoft Teams. <br/> |Descargue el archivo desde el cliente web o en SharePoint Online <br/> |10/5/2019  <br/> |

## <a name="teams"></a>Microsoft Teams

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los registros de auditoría pueden notificar un nombre de usuario incorrecto como iniciador cuando se ha eliminado a alguien de un equipo  <br/> |El equipo de Microsoft Teams es un grupo moderno en AAD. Cuando se agregan o se quitan miembros mediante la interfaz de usuario de Teams, el flujo sabe exactamente quién fue el usuario que inició el cambio y el registro de auditoría refleja la información correcta. Sin embargo, si un usuario agrega o quita un miembro mediante AAD, el cambio se sincroniza en el backend de Microsoft Teams sin informar a Teams acerca de quién inició la acción. Microsoft Teams considera que el primer propietario del equipo es el iniciador, lo que se verá finalmente reflejado en el registro de auditoría.    <br/> |  <br/> |11/05/2018  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La carga de fotos en Teams no está bloqueada en OWA/Outlook como requiere la directiva   <br/> | Teams permite a los usuarios cargar fotos directamente en Office 365, a pesar de la configuración de la directiva que hay en vigor para evitar que se carguen fotos en OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de equipos públicos no incluye a todos los equipos.  <br/> |La lista de equipos públicos está basada en Microsoft Graph.  <br/> |Si no ve un equipo, pruebe a buscarlo en el cuadro de la parte superior derecha. Además, los propietarios de equipos deben comunicar los nombres de equipos a sus compañeros, ya que pueden aparecer muchos equipos en los resultados de la búsqueda. <br/> | 21/07/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los nombres de equipo que contienen caracteres especiales pueden crear errores en la creación de reuniones  <br/> |El usuario recibirá el mensaje **se ha producido un error** de color rojo cuando intente crear una reunión de un equipo que tenga caracteres especiales en el nombre.   <br/> |Cambie el nombre o vuelva a crear el equipo con un nombre que no contenga "/".  <br/> |13/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Un nombre de equipo que tenga un símbolo &amp; rompe la funcionalidad del conector  <br/> |Cuando se crea un nombre de equipo e incluye el símbolo &amp;, no pueden establecerse los conectores dentro del equipo/grupo.  <br/> |No se deben usar caracteres especiales en los nombres de equipo.  <br/> |21/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El límite máximo de miembros de un equipo es 5000.  <br/> |Cada equipo de Microsoft Team puede tener un máximo de 5000 miembros por equipo.  <br/> |No hay ninguna solución.  <br/> |6/2/2019  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Al eliminar un equipo, también se elimina el grupo que está asociado a él.  <br/> |Es posible que los usuarios no se percaten de que el grupo de Office 365 subyacente se elimina cuando se elimina el equipo. Además, si se elimina el grupo de Office 365 subyacente, el equipo se elimina también.  <br/> |Un idioma adicional en Microsoft Teams proporciona esta información al usuario. Esta información no está presente en la interfaz de grupos de Office 365. El servicio de asistencia puede recuperar un grupo o equipo eliminado.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La aplicación de escritorio de Microsoft Teams muestra una pantalla blanca  <br/> | <br/> |Intente eliminar o reinstalar los controladores gráficos del equipo, o iniciar Teams desde una línea de comandos con la marca Deshabilitar GPU:<ul><li>Para Windows: Abra el símbolo del sistema y especifique lo siguiente: `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Para Mac: Inicie Terminal y especifique lo siguiente: `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El usuario no recibe el correo electrónico de bienvenida cuando se le agrega de forma administrativa  <br/> |Cuando se agrega a un miembro a un equipo con PowerShell o el centro de administración de Teams, este no recibe el mensaje de bienvenida de Microsoft Teams  <br/> |Agregar a un miembro directamente desde la interfaz de usuario de Teams enviará un correo electrónico. Actualmente, no hay ninguna solución alternativa a hacerlo de forma administrativa.  <br/> |12/2/19  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden mover, eliminar o cambiar el nombre de archivos después de la edición  <br/> |No se puede mover, eliminar o cambiar el nombre de un archivo inmediatamente después de editarlo en Teams. <br/> |Esto es un problema conocido actualmente y la solución es esperar algún tiempo antes de realizar los cambios administrativos.  <br/> |12/03/19  <br/> |
