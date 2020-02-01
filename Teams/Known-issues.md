---
title: Problemas conocidos de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 6/25/2019
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
description: Lista actual de problemas conocidos en la aplicación cliente de Microsoft Teams y en la experiencia de los administradores.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c613f2116b5ad9f97426f60466d71d4ffaddba1
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628536"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conocidos de Microsoft Teams

En este artículo se indican los problemas conocidos de Microsoft Teams por área de características.

## <a name="administration"></a>Administración

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La directiva de EAF del Kit de herramientas de Experiencia de mitigación mejorada (EMET) puede identificar incorrectamente las optimizaciones del espacio aislado de Chromium como amenazas. <br/> |Hay un problema con el espacio aislado de Chromium en el que la directiva de exportación del filtrado de acceso a la tabla de direcciones (EAF) del Kit de herramientas de Experiencia de mitigación mejorada (EMET) y de la Protección contra amenazas avanzada (ATP) de Windows Defender puede identificar incorrectamente las optimizaciones del espacio aislado de Chromium como amenazas. Esto hace que Teams no funcione correctamente.  <br/> | Para solucionar este problema, desactive EAF en Microsoft Teams. Puede leer más información sobre el problema en las [Instrucciones de mitigaciones de EMET](https://support.microsoft.com/help/2909257/emet-mitigations-guidelines). Para obtener más información sobre la directiva de EAF y de la Protección contra amenazas avanzada de Microsoft Defender, vea [Habilitar la protección contra vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection). <br/> |11/10/2018 <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden agregar miembros a los equipos cuando UsersPermissionToReadOtherUsersEnabled está establecido como falso  <br/> |Cuando este valor se establece como falso en AAD, el cliente no puede agregar miembros externos o internos en Microsoft Teams, y aparece el siguiente mensaje de error: "No se han podido agregar los miembros. Ha surgido un problema. Inténtelo de nuevo más tarde". Sin embargo, los miembros se pueden agregar directamente en los grupos de Office 365.    <br/> |En AAD, cambie este ajuste a verdadero.  <br/> |10/4/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La administración de conectores a nivel de inquilino ya no está disponible  <br/> |Al intentar agregar un conector en la versión de cliente y la versión en línea, se recibe el error: Se ha producido un error inesperado. Inténtalo de nuevo. Set-OrganizationConfig -ConnectorsEnabled=True   <br/> |Deshabilítelo en la configuración de Microsoft Teams. Vea este artículo de soporte: https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21/6/17  <br/> |

## <a name="apps"></a>Aplicaciones

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que [Acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) no funcione cuando use la pestaña "Sitio Web" en la aplicación de escritorio<br/> |Si un sitio web, por ejemplo, un portal de intranet, cuenta con directivas de acceso condicional (como restricciones en el explorador o las direcciones IP), ese sitio web puede no parecer como una pestaña dentro de Teams en la aplicación de escritorio <br/> |Usar Teams en un explorador en lugar de en la aplicación de escritorio.  <br/> |1/7/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Faltan opciones de conector para algunos equipos  <br/> |Cuando se hace clic con el botón derecho en un canal, la opción Conectores no aparece para ningún miembro del equipo.  <br/> |El usuario que cree el equipo debe tener un buzón en línea; de lo contrario, la opción Conector no estará disponible. Este es el comportamiento que se espera.  <br/> |26/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La aplicación "Tareas" permanece visible cuando se deshabilita  <br/> |Cuando se deshabilita la aplicación "Tareas" en el centro de administración, permanece visible en el cliente de Teams para los usuarios con licencia EDU. Si se selecciona cuando está deshabilitada, aparece el mensaje de error: "¡Vaya! Ha habido un problema..."  <br/> |No hay ninguna solución.  <br/> |29/12/2017  <br/> |

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
|Información de interoperabilidad de vídeo en la nube en Reunirse ahora  <br/> |Si crea una instancia Reunirse ahora de una reunión en Microsoft Teams con una licencia CVI existente, la información de CVI no se completará. <br/> |Le recomendamos programar la reunión para completar esta información.  <br/> |11/6/2019  <br/> |

## <a name="authentication"></a>Autenticación

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando intenta unirse a Teams desde Internet Explorer o Microsoft Edge, el programa lo intenta constantemente o se bloquea y no consigue iniciar sesión.
   <br/> | Su organización utiliza los sitios de confianza de Internet Explorer y la aplicación basada en web de Teams no logra iniciar sesión correctamente porque los sitios de confianza de Teams no están permitidos. <br/>|Haga los siguientes cambios en la configuración de IE o desde el Panel de control, ya sea con derechos de administrador o con un objeto de directiva de grupo:<br/><ol><li>En **Opciones de Internet** &gt; **Privacidad** &gt; **Avanzada**, acepte las cookies de origen y de terceros, y active la casilla **Aceptar siempre las cookies de sesión**.</li><li>Haga clic en **Opciones de Internet** &gt; **Seguridad** &gt; **Sitios de confianza** &gt; **Sitios** y agregue lo siguiente:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>NOTA</b>: Valide y permita siempre todas las direcciones URL de confianza de Teams y los requisitos del siguiente documento: [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

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
|No se puede iniciar Microsoft Teams para Surface Hub desde Microsoft Store |Microsoft Teams para Surface Hub no se inicia al hacer clic en **Iniciar** en Microsoft Store. | El lanzamiento de la aplicación Teams para Surface Hub desde la lista de Microsoft Store no es compatible con Windows en Surface Hub. <br> <br/> Reinicie Surface Hub después de instalar Teams. | 27/02/18 |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams no actualiza automáticamente   <br/> | Cuando Microsoft Teams se instala en Archivos de programa mediante scripts de instalación en vez de la ubicación predeterminada, el cliente no actualiza automáticamente cuando aparecen nuevas versiones.    <br/> | Deliberado. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El vínculo simbólico o la asignación de una unidad a C:\Usuarios hace que la aplicación se inicie en una pantalla blanca  <br/> | Cuando Microsoft Teams se instala en Archivos de programa mediante scripts de instalación en vez de la ubicación predeterminada, el cliente no actualiza automáticamente cuando aparecen nuevas versiones.   <br/> | Deliberado. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`. Si la asignación es necesaria, deberá usar la versión web de Microsoft Teams.  <br/> | 07/09/2017  <br/> |

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

## <a name="linux"></a>Linux

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El inicio automático en Linux no funciona. <br/> |El inicio automático en Linux no inicia la aplicación de Teams. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Pantalla en blanco al reanudar desde el modo de suspensión. <br/> |Cuando el equipo se reanuda o se reactiva del modo de suspensión, puede haber un cambio en la red (especialmente cuando el equipo está conectado a la VPN antes de activar el modo suspensión), por lo que el equipo tarda en volver a obtener la conexión. La combinación de estas cosas puede dar lugar a la pantalla en blanco de Teams. <br/> |Puede ser útil reiniciar el cliente de Teams.  <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Falta un cursor cuando se comparte la pantalla. <br/> |Cuando se comparte la pantalla, la otra parte no ve el cursor de la persona que comparte la pantalla. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Problema en la ejecución en paralelo con la estación de trabajo VMWare. <br/> |La aplicación Teams experimenta problemas al funcionar en paralelo con la estación de trabajo VMWare. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las notificaciones de KDE crean una barra de tareas nueva.<br/> |Las notificaciones de KDE crean una ventana nueva en la barra de tareas. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los administradores de paquetes no muestran la lista de cambios. <br/> |El administrador de paquetes no muestra la lista de cambios. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede iniciar el cliente de Teams en el modo sin conexión. <br/> |No se puede iniciar Teams sin conexión en un cliente Linux. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Configuración del dispositivo durante una reunión. <br/> |Cuando se encuentre en una reunión y cambie la configuración del dispositivo, el indicador del micrófono no registra nada que se esté detectando. <br/> | <br/> |05/12/19  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede cerrar la aplicación Teams con el teclado. <br/> |No se puede cerrar la aplicación Teams con el `$mod + shift + q` predeterminado o haciendo clic en el botón cerrar de la aplicación. <br/> | <br/> |05/12/19  <br/>|

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
|No hay audio mientras se comparte contenido durante una reunión de difusión  <br/> |Al compartir el contenido durante una difusión de reunión, los participantes no pueden oír el audio del contenido compartido (vínculo de youtube o archivo de vídeo guardado).  <br/> |Ninguna, ya que se ha diseñado así.  Teams actualmente no admite audio del contenido compartido  <br/> |09/10/2018  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No puede iniciar la reunión como organizador de Outlook, ya que es posible que quede atascada en la sala de espera virtual  <br/> |Es posible que tenga este problema por que el cliente de Outlook y el de equipos iniciaron sesión en cuentas diferentes. <br/> |Cuando se una a la reunión, asegúrese de que el cliente de Outlook y de equipos estén conectados a la misma cuenta en la que se programó la reunión.  <br/> |5/11/18  <br/> |

## <a name="mobile"></a>Móvil

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se pueden ver los canales marcados como favoritos automáticamente  <br/> |Algunos miembros no pueden ver los canales marcados como favoritos automáticamente en la aplicación móvil.  <br/> |Los miembros deben iniciar sesión primero en la aplicación de escritorio o en la aplicación web para ver los canales marcados como favoritos automáticamente en sus aplicaciones móviles.  <br/> |30/04/2018  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Problemas que pueden surgir al usar iOS 13 beta  <br/> |1. Las notificaciones de Teams no se activan.  Esto incluye chats, menciones y llamadas.  2. La vista previa del archivo no funciona con la compilación beta.  <br/> |No hay ninguna solución en este momento.  Estamos trabajando con desarrolladores de Apple para encontrar correcciones para estos problemas.  <br/> | 25/06/2019  <br/>|


## <a name="people"></a>Personas

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Fotos de perfiles de usuario  <br/> | Actualmente, Teams no tiene un mecanismo para impedir que los usuarios cambien la foto. El equipo de BTS se ha reunido con el equipo de desarrollo que ha registrado el siguiente tema para su consideración: Característica 108874: Directiva de TI para deshabilitar la carga de fotos de perfil   <br/> | Si tiene clientes que desean tener la posibilidad de impedir la carga de fotos de perfilen Teams, avíseles que pueden agregar su voto y su caso de negocio en los comentarios: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |



## <a name="phone-system"></a>Sistema telefónico

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Departamento de cuentas de recursos mal configuradas  <br/> | Las cuentas de recursos locales asociadas con un operador automático o una cola de llamada creados antes de enero de 2019 puede que no tengan el parámetro Department configurado correctamente, lo que podría provocar una asignación errónea de números de teléfono. Se está realizando una corrección para resolver este problema. <br/><br/> Las cuentas de recursos configuradas mediante el uso de New-CsHybridApplicationEndpoint con Skype Empresarial Server no tendrán el parámetro Department configurado correctamente, lo que provocará errores en la creación de cuentas de recursos en el centro de administración de Teams. En este caso, debe configurar el nombre del departamento en Active Directory local antes de la sincronización en línea.|Para mitigar este problema, puede ejecutar el siguiente Cmdlet para configurar el parámetro de departamento. Set-MsolUser -ObjectId <Resource Account Object ID> : Department "Microsoft Communication Application Instance" <br/> Vea también el [operador automático y la actualización del servicio de colas de llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521). |8/5/19 <br/> |


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Retraso de sincronización de cuentas de recursos|No se puede asignar un número de teléfono a la cuenta del recurso o se recibe el error "la siguiente instancia de la aplicación no está presente en BVD".|Espere 24 horas para sincronizar. Si ya ha transcurrido 24 horas, quite la asignación de números de teléfono, elimine la cuenta de recurso y cree una nueva con un nombre diferente.|18/05/2019|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede asignar un número de servicio de teléfono desde el centro de administración de equipos|Cuando intenta asignar un número de servicio de telefonía en el centro de administración de equipos, recibe el error "necesita una licencia de sistema telefónico".|Use los cmdlets de PowerShell para asignar un número de servicio de pago en su lugar.|18/05/2019|


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuenta de recurso dañada|La cuenta de recursos no funciona|Quitar o reemplazar la licencia de la cuenta de un recurso, o crear una nueva cuenta de recursos con el mismo URI del SIP que la eliminada anteriormente, producirá una cuenta de recursos dañada.|18/05/2019|


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Número de teléfono bloqueado|Número de teléfono bloqueado: al eliminar la cuenta del recurso antes de quitar el número de teléfono, se bloquea el número de teléfono.|Póngase en contacto con el soporte técnico de Microsoft para liberar el número de teléfono.|18/05/2019|

## <a name="presence"></a>Presence
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La presencia en la aplicación de Outlook, o en otras aplicaciones de Office, no se muestra después de que un usuario se mueva al modo **Teams solo**. <br/> |Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams.  <br/> |Para ver la presencia en Outlook (y en otras aplicaciones de Office), debe tener instalado Skype Empresarial, incluso si está ejecutando Teams en modo **Teams solo**. Microsoft es consciente de este problema y está buscando una solución.   <br/> |9/2019  <br/> |



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
|Integración de Teams Planner con Planner Online <br/> |Los propietarios no pueden crear un plan desde un equipo creado a partir de un grupo existente de Office 365.  <br/> |Conceda permisos de miembro para el propietario del grupo. <br/> |14/1/20  <br/>|




|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Ficha OneNote heredada  <br/> |Las fichas OneNote heredadas que se crearon durante la versión preliminar pública de Microsoft Teams no se pueden eliminar ni se les puede cambiar el nombre.  <br/> |No hay ninguna solución. <br/> |8/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Función de búsqueda en la pestaña de lista de SharePoint  <br/> |Si se intenta abrir un archivo desde la función de búsqueda de la pestaña de lista de SharePoint, aparecerá un aviso "Necesitará una nueva aplicación para abrir este archivo" y el archivo no se abrirá. <br/> |Abra directamente desde la lista en lugar de la barra de búsqueda. <br/> |11/2/2019  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Error de descarga de archivos <br/> |Intentar descargar un archivo cuando la ruta del archivo contiene un apóstrofo desencadenará un error "El archivo no se ha descargado" al usar al cliente de escritorio de Microsoft Teams. <br/> |Descargue el archivo desde el cliente web o en SharePoint Online <br/> |10/5/2019  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede cargar o descargar el archivo de OneNote <br/> |Si intenta cargar o descargar un archivo o bloc de notas de OneNote con Microsoft Teams, se producirá un error. <br/> |Descargar o cargar el archivo directamente en SharePoint Online <br/> |7/5/2019  <br/> |

## <a name="teams"></a>Teams

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los correos de voz de Teams llegarán con un mensaje de error spf si es una llamada sip, si es una llamada pstn a un usuario llegarán con el atributo from sin el valor correcto, si el cliente tiene una regla donde analiza los correos de voz spf tendrá la acción donde el etr decide. <br/> | <br/> | El 29/08/2019 se añadirá una excepción en el etr si el mensaje es un mensaje de voz.


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La carga de fotos en Teams no está bloqueada en OWA/Outlook como requiere la directiva   <br/> | Teams permite a los usuarios cargar fotos directamente en Office 365, a pesar de la configuración de la directiva que hay en vigor para evitar que se carguen fotos en OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de equipos públicos no incluye a todos los equipos.  <br/> |La lista de equipos públicos está basada en Microsoft Graph.  <br/> |Si no ve un equipo, pruebe a buscarlo en el cuadro de la parte superior derecha. Además, los propietarios de equipos deben comunicar los nombres de equipos a sus compañeros, ya que pueden aparecer muchos equipos en los resultados de la búsqueda. <br/> | 21/07/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los nombres de equipo que contienen caracteres especiales pueden crear errores en la creación de reuniones  <br/> |El usuario recibirá el mensaje **se ha producido un error** en color rojo cuando intente crear una reunión para un equipo que tenga caracteres especiales en el nombre.   <br/> |Cambie el nombre o vuelva a crear el equipo con un nombre que no contenga "/".  <br/> |13/07/2017  <br/> |

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
|Problema de interoperabilidad entre Symantec DLP y Teams <br/> |Los agentes de Endpoint de Symantec DLP pueden interferir con el proceso de Teams, lo que puede provocar un error en el inicio o cierre.  <br/> |Excluya (añada a la lista blanca) Teams.exe de los agentes de Endpoint de Symantec DLP tal y como se describe en este <a href="https://support.symantec.com/us/en/article.TECH220322.html">artículo de soporte técnico de Symantec</a>. <br/> |15/07/19  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El cifrado Dell puede impedir que Teams se inicie <br/> |El cifrado Dell (anteriormente el cifrado de protección de datos Dell) puede dañar la instalación de Teams durante el proceso de actualización, lo que provoca un error permanente al iniciar la aplicación. <br/> |Excluya la carpeta Teams en %LocalAppData%\Microsoft\Teams de la directiva de cifrado. <br/> |21/11/19  <br/> |
