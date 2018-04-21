---
title: Problemas conocidos de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 4/18/2018
ms.topic: article
ms.service: msteams
ms.reviewer: marcl, ninadara, v-leslc
description: Lista actual de problemas conocidos en la aplicación cliente de Microsoft Teams y en la experiencia de los administradores.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c8ce7b7d53e03ae265f41105dabd09978a62e61
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conocidos de Microsoft Teams
  
Este artículo enumera los problemas conocidos de Microsoft Teams, por área de característica.
## 

## <a name="administration"></a>Administración
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Admin administración de inquilinos todo conectores ya no está disponible  <br/> |Al intentar agregar un conector de cliente y versión en línea obtenemos el error: error inesperado. Vuelva a intentarlo. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Deshabilitar la configuración de los equipos. Consulte el artículo de soporte técnicohttps://msdn.microsoft.com/en-us/microsoft-teams/connectors  <br/> |21/06/2017  <br/> |

## <a name="apps"></a>Aplicaciones
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Opciones del conector es falta para algunos equipos  <br/> |Cuando se hace clic con el botón derecho en un canal, la opción Conectores no aparece para ningún miembro del equipo.  <br/> |El usuario que cree el equipo debe tener un buzón en línea; de lo contrario, la opción Conector no estará disponible. Este es el comportamiento que se espera.  <br/> |26/06/2017  <br/> |

## <a name="authentication"></a>Autenticación
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando intenta unirse a Teams desde Internet Explorer o Edge, el programa lo intenta constantemente o se bloquea y no consigue iniciar sesión.   <br/> | Su organización utiliza los sitios de confianza de Internet Explorer y la aplicación basada en web de Teams no logra iniciar sesión correctamente porque los sitios de confianza de Teams no están permitidos. <br/>|Haga los siguientes cambios en la configuración de IE, ya sea con los derechos de administrador o con un objeto de directiva de grupo:<br/><ol><li>En **Opciones de Internet** &gt; **Privacy** &gt; **Avanzadas**, Aceptar cookies y de terceros y la casilla de verificación para **Permitir siempre las cookies de sesión**.</li><li>Haga clic en **Opciones de Internet** &gt; **Sitios de confianza** &gt; **sitios**y agregue lo siguiente:<ul><li>https://\*.microsoft.com</li><li>https://\*.microsoftonline.com</li><li>https://\*.teams.skype.com</li><li>https://\*.teams.microsoft.com</li><li>https://\*.sfbassets.com</li><li>https://\*.skypeforbusiness.com</li></ul></li></ol><br/><b>NOTA</b>: Valide y permita siempre todas las direcciones URL de confianza de Teams y los requisitos del siguiente documento: [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).   <br/> |01/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Limitaciones de complementos de Outlook  <br/> |Para usar el complemento de Outlook, debe iniciar sesión en Microsoft Teams con la autenticación multifactor. Si se produce un error en la autenticación multifactor durante el proceso de inicio de sesión, podrá iniciar sesión en Microsoft Teams, pero recibirá un mensaje de error cuando intente usar el complemento.  <br/> Por el momento, el complemento solo está disponible para los usuarios de Windows.  <br/> El complemento no funcionará si usa un proxy de autenticación.  <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Teams de Microsoft siempre se registrará en la cuenta de equipo unido al dominio.   <br/> |Si un usuario tiene dos cuentas distintas de equipos y tiene una máquina con Unidos a un dominio permitido, equipos usarán el perfil Unidos a un dominio en el equipo para que el usuario iniciará sesión automáticamente en los equipos. Para cambiar a la otra cuenta de equipos, el usuario debe cerrar la sesión de la aplicación manualmente y escriba credenciales para la segunda cuenta para iniciar sesión. Si el usuario cierra sesión en equipos y reinicia el equipo, al reiniciarse, equipos iniciará la sesión automáticamente con el perfil de dominio. <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Error de autenticación modernos - aut no habilitado  <br/> |Cuando se produce un error inicial en la autenticación multifactor, use la aplicación web para la autenticación.  <br/> Para obtener más información, consulte [Servicios de federación de Active Directory prompt=login parameter support](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Compruebe esta configuración: Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled.  <br/> |19/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Planificador de compilación de inicio de sesión único (SSO) <br/> |El inicio de sesión único no se aplica en Planner. Tendrá que volver a iniciar sesión la primera vez que use Planner en cada cliente.  <br/> |No hay ninguna solución. Estamos trabajando en otras mejoras para la autenticación.  <br/> |28/02/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede guardar la imagen de perfil.  <br/> |Los usuarios no pueden guardar su imagen de perfil cuando el buzón de Exchange está hospedado (alojado) localmente.  <br/> |No hay ninguna solución.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Explorador
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Aparecen anomalías verdes en las imágenes cuando se presenta un vídeo en Chrome.  <br/> |Verde artefactos aparecen al ver vídeos o compartir la pantalla en una llamada o meetup en cromo.  <br/> |Deshabilite la configuración de aceleración de hardware en Chrome.  <br/> |03/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Compatibilidad con el cliente web de Safari  <br/> |A los usuarios que intentan abrir el cliente web de Microsoft Teams en Safari se les redirige al sitio de descarga del cliente de escritorio. Microsoft está investigando la compatibilidad con Safari y compartirá las actualizaciones a través del [mapa de ruta de Microsoft Teams](http://aka.ms/TeamsRoadmap).  <br/> |Utilizar los exploradores de internet, que incluyen: Internet Explorer 11 +, Microsoft Edge 12 +, cromo 51.0 + y Firefox 47.0 +.  <br/> |02/11/2016  <br/> |

## <a name="channels"></a>Canales
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando un usuario abandona la empresa, aparece en Teams de Microsoft como "Usuario desconocido"<br/> |Cuando un usuario abandona la empresa, aparece en Teams de Microsoft como "Usuario desconocido". Además, se muestra la ficha de la conversación: "usuario desconocido se ha agregado al equipo." Problema de archivado como:https://domoreexp.visualstudio.com/MSTeams/_workitems/edit/168830  <br/> |No hay ninguna solución.  <br/> |9/12/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden volver a crear un nombre de canal que haya existido anteriormente.  <br/> |Una vez que se crea el nombre de un canal, este no se puede volver a usar, incluso si se ha eliminado. Nuestro sistema mantiene estos datos para posibles situaciones de protección de información.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

## <a name="chat"></a>Chat

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las menciones @ por mensaje eliminado enviar notificación con enlace de canal  <br/> |Hay una limitación conocida de notificación cuando esté en el mencionado en un mensaje que se elimina; la notificación de la fuente se desplazará al canal, pero no para un mensaje específico. <br/> | Por diseño <br/> | 28/3/17  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios locales de Skype Empresarial no reciben mis mensajes.  <br/> |Los mensajes no se completarán cuando los usuarios de Microsoft Teams intenten enviar un mensaje a otra persona que esté usando Skype Empresarial local.  <br/> | Se admite la interoperabilidad entre Microsoft Teams y los usuarios que están alojados en Skype Empresarial Online. Los usuarios de Microsoft Teams pueden enviar chats entre dos personas a usuarios que no pertenezcan a Microsoft Teams con Skype Empresarial Online. <br/> No se admite la interoperabilidad entre Microsoft Teams y los usuarios que están alojados en Skype Empresarial local. Los usuarios de Microsoft Teams no pueden enviar chats entre dos personas a usuarios que no pertenezcan a Microsoft Teams con Skype Empresarial local.  <br/> |02/11/2016  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios locales de Skype Empresarial no reciben mis mensajes.  <br/> |Los mensajes no se completarán cuando los usuarios de Microsoft Teams intenten enviar un mensaje a otra persona que esté usando Skype Empresarial local. <br/> | Se admite la interoperabilidad entre Microsoft Teams y los usuarios que están alojados en Skype Empresarial Online. Los usuarios de Microsoft Teams pueden enviar chats entre dos personas a usuarios que no pertenezcan a Microsoft Teams con Skype Empresarial Online. <br/> No se admite la interoperabilidad entre Microsoft Teams y los usuarios que están alojados en Skype Empresarial local. Los usuarios de Microsoft Teams no pueden enviar chats entre dos personas a usuarios que no pertenezcan a Microsoft Teams con Skype Empresarial local. <br/> |02/11/2016  <br/> |

## <a name="client"></a>Cliente
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los equipos no se actualiza automáticamente   <br/> | Cuando se instala Microsoft Teams a archivos de programa mediante secuencias de comandos de instalación en lugar de en la ubicación predeterminada, el cliente no actualizará automáticamente cuando estén disponibles nuevas versiones.    <br/> | Por diseño. Asegúrese de instalar la aplicación en la ubicación predeterminada: user\Appdata.  <br/> | 9/7/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Symlink o mappying una unidad a C:\users hace que la aplicación debe iniciar pantalla en blanco  <br/> | Cuando se instala Microsoft Teams a archivos de programa mediante secuencias de comandos de instalación en lugar de en la ubicación predeterminada, el cliente no actualizará automáticamente cuando estén disponibles nuevas versiones.   <br/> | Por diseño. Asegúrese de instalar la aplicación en la ubicación predeterminada: user\Appdata. Si la asignación debe existir, debe utilizar la versión web de Microsoft Teams.  <br/> | 9/7/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Vínculo simbólico o asignar una unidad a c:\users hará que la aplicación debe iniciar pantalla en blanco  <br/> |Cuando la ubicación predeterminada de C:\users\<usuario > \appData se cambia al mover la carpeta C:\users o mediante vínculos simbólicos, la aplicación se iniciará con una pantalla en blanco.   <br/> |No hay ningún trabajo conocido alrededor. Si la asignación debe existir, debe utilizar la versión web de Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Entorno de
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los buzones de grupo no están habilitados para poder archivar en ellos (almacenamiento extra).  <br/> |En el Centro de seguridad y cumplimiento de Office 365, los administradores globales no pueden habilitar el archivado en los buzones de grupo. Solo pueden hacerlo en los buzones de los usuarios.  <br/> |Si la capacidad del buzón de grupo está casi llena, póngase en contacto con el soporte técnico de Microsoft Office para ampliar el tamaño del buzón.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Acceso como invitado
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los clientes de la UE y APAC reciben un error cuando agregan un usuario invitado desde otro inquilino    <br/> | Los clientes de la UE y APAC sufren un retraso en la replicación entre Microsoft Teams y Azure Active Directory. Cuando un usuario de un inquilino de UE o APAC intenta agregar un usuario invitado desde otro inquilino, recibe un mensaje de error indicando que vuelva a intentarlo.   <br/> |Haga clic en el botón para reintentar y vuelva a realizar la adición del usuario invitado.  <br/> |08/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se ha creado una wiki para los canales que creen los invitados.  <br/> |Cuando un invitado crea un canal, no se crea la ficha **Wiki**. La ficha **Wiki** no se puede adjuntar manualmente al canal. <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

## <a name="meetings"></a>Reuniones.
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden tener acceso a las reuniones o conectores pero tienen buzones de Exchange Online. <br/> |Cliente activamente bloquea EWS desde los servicios de Exchange Online, pero necesita tener MS Teams compatibles dentro de las políticas EWS. <br/> |Para hacer que MS Teams compatible, debe agregar la siguiente cadena de agente de usuario para MS Teams de la EWSAllowList: *skypespaces*, incluidos los asteriscos. El comando completo es: set-organizationconfig - ewsallowlist *skypespaces*<br/> Para obtener más información:https://technet.microsoft.com/en-us/library/aa997443(v=exchg.160).aspx <br/> |30/5/17  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se necesita Skype Empresarial para algunas reuniones.  <br/> |Para su comodidad, su calendario de citas se muestra en Microsoft Teams. Para entrar en una reunión, solo tiene que hacer clic en el botón **Unirse**. <br/> Mientras trabajamos para seguir desarrollando esta área, si esta reunión se programó con Skype Empresarial, cuando haga clic en **Unirse**, Microsoft Teams iniciará su cliente de Skype Empresarial para que pueda terminar de entrar en la reunión. Las reuniones que se programaron en Microsoft Teams se iniciarán directamente en este producto.  <br/> En el futuro, simplificaremos esta experiencia.  <br/> |Haga clic en **Unirse**. Microsoft Teams decidirá de manera inteligente si es necesario Skype Empresarial para que un usuario se una a la reunión en función de la dirección URL que se ha incluido en la descripción de la reunión.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Falta de **reuniones**ser descubiertos mediante la detección automática de Exchange. <br/> Teams de Microsoft aún no admite los buzones de Exchange alojados en icono de la barra de navegación izquierda <br/> |El icono **reuniones** en la barra de la aplicación está actualmente sólo habilitado para los usuarios cuyo buzón está en multiempresa de Office 365 y select pocos dedicado a los usuarios cuya ubicación de buzón puede - locales y dedicado de Exchange. Estamos investigando esta situación, pero aún no hay una fecha estimada para esta funcionalidad.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Número máximo de asistentes para las reuniones  <br/> |Cada reunión de Microsoft Teams puede albergar un máximo de 80 asistentes.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las reuniones no están disponibles.  <br/> |El icono y la funcionalidad de las reuniones no están disponibles cuando el buzón de Exchange está hospedado (alojado) localmente.  <br/> |Actualice a la actualización acumulada 3 de Exchange 2016 o posterior para la implementación local.  <br/> |28/02/2017  <br/> |

## <a name="mobile"></a>Móvil
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede utilizar diversión selector o Giphys o adhesivos en aplicaciones móviles  <br/> |No puede utilizar archivos GIF, emojis o etiquetas en los clientes móviles.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Diferencias de diseño de los equipos de cliente móvil  <br/> |Los equipos aparecen en orden alfabético y los canales no se puede contraer en el cliente móvil.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|

## <a name="people"></a>Personas
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Fotos de perfil de usuario  <br/> | Actualmente los equipos no tiene un mecanismo para impedir que los usuarios cambien de fotos. Se ha encontrado el equipo BTS con el equipo de desarrollo que haya presentado la siguiente consideración: característica 108874: directiva de TI para deshabilitar la carga de la imagen de perfil   <br/> | Si tiene clientes que desean que la capacidad de evitar cargar foto en el perfil en los equipos, deben agregar su caso voto y negocio a comentarios aquí:https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos
 <br/> |1/3/17 <br/> |

## <a name="provisioning"></a>Provisioning
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se ha creado un usuario de SharePoint incorrecto para el sitio de SharePoint en Microsoft Teams.  <br/> |El administrador de SharePoint aparece como el creador de SharePoint para un grupo de Microsoft Teams, en lugar del usuario correcto.  <br/> Cuando se realiza una auditoría desde la consola de administración de SharePoint, el creador de la página de colección de sitios asociada con el grupo de Office 365 que se crea con el equipo de Microsoft Teams es el administrador de SharePoint.  <br/> |No hay ninguna solución.  <br/> |21/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden crear un equipo.  <br/> |Es posible que su empresa haya establecido una directiva para restringir quién puede crear equipos o grupos de Office 365.  <br/> |Compruébelo con su administrador de TI para saber cuál es la directiva de su empresa en relación con la creación de grupos y equipos.  <br/> |13/03/2017  <br/> |

## <a name="tabs"></a>Fichas
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Pestañas que no funcionan desde que se habilitó el acceso condicional <br/> |Algunas fichas no se carga ya en el cliente de escritorio desde que se habilitó el acceso condicional a los inquilinos. Las fichas se cargarán cuando utiliza al cliente Web. Algunas fichas que podrían verse afectadas son: PowerBI, formularios, VSTS, PowerApps y lista de SharePoint.  <br/> |Para ver las fichas afectadas debe utilizar equipos de arista, IE o Chrome con la extensión de las 10 cuentas de Windows instalada. Algunas fichas todavía dependen de la autenticación web, que no funciona en el cliente de escritorio cuando la entidad emisora de certificados está habilitada. Trabajamos con socios para habilitar estos escenarios; hasta ahora hemos habilitado planificador, OneNote y secuencia. <br/> |4/5/18  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de espacios de trabajo no está ordenada alfabéticamente.  <br/> |Los usuarios que tienen que cambiar de espacio de trabajo cuando agregan una ficha PowerBI verán que la lista de espacios de trabajo entre los que tienen que alternar no está ordenada alfabéticamente.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La barra de desplazamiento desaparece cuando se seleccionan informes.  <br/> |Cuando los usuarios que agregan informes de PowerBI intentan desplazarse por una lista que es más extensa que la pantalla de los informes no pueden evitar que se pierda la barra de desplazamiento.  <br/> |Use la flecha arriba o la flecha abajo para desplazarse por la lista.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Equipos planificador integración con Planner en línea <br/> |Depósitos de tareas en el planificador no se muestran en la experiencia en línea de planificador.  <br/> |No hay ninguna solución. <br/> |28/02/2017  <br/>|

## <a name="teams"></a>Microsoft Teams
|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La carga de fotos en Teams no está bloqueada en OWA/Outlook como requiere la directiva   <br/> | Teams permite a los usuarios cargar fotos directamente en Office 365, a pesar de la configuración de la directiva que hay en vigor para evitar que se carguen fotos en OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de equipos públicos no incluye a todos los equipos.  <br/> |La lista de equipos públicos está basada en Microsoft Graph.  <br/> |Si no ve un equipo, pruebe a buscarlo en el cuadro de la parte superior derecha.  <br/> | 21/07/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Nombres de equipo que contienen caracteres especiales pueden crear errores de creación de la reunión  <br/> |Usuario recibirá el mensaje **error** en rojo al intentar crear una reunión para un equipo que tenga caracteres especiales en el nombre.   <br/> |Cambiar el nombre o volver a crear el equipo con un nombre que no contenga un "/".  <br/> |13/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El nombre de un equipo con un &amp; símbolo en él rompe la funcionalidad de conector  <br/> |Cuando se crea un nombre de equipo e incluye el símbolo &amp;, no pueden establecerse los conectores dentro del equipo/grupo.  <br/> |No se deben usar caracteres especiales en los nombres de equipo.  <br/> |21/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El límite máximo de miembros de un equipo es 2500.  <br/> |Cada equipo de Microsoft Teams puede incluir un máximo de 2500 miembros por equipo.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Al eliminar un equipo, también se elimina el grupo que está asociado a él.  <br/> |Es posible que los usuarios no se percaten de que el grupo de Office 365 subyacente se elimina cuando se elimina el equipo. Además, si se elimina el grupo de Office 365 subyacente, el equipo se elimina también.  <br/> |Un idioma adicional en Microsoft Teams proporciona esta información al usuario. Esta información no está presente en la interfaz de grupos de Office 365. El departamento de soporte puede recuperar un grupo/equipo eliminado.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|  
|Aplicación de escritorio de los equipos que muestra la pantalla en blanco  <br/> | <br/> |Intente eliminar o reinstalar a los controladores de gráficos en el equipo o iniciar los equipos desde una línea de comandos con un marcador para deshabilitar el GPU:<ul><li>Para Windows: Abra el símbolo del sistema y escriba lo siguiente: cd %localappdata%\microsoft\teams\current ejecutar Teams.exe--disable-gpu</li><li>Terminal para Mac: Inicio y escriba lo siguiente: cd \Applications carpeta Microsoft\ Teams.app/Contents/MacOS/Teams--disable-gpu</li></ul> <br/> |<br/> |

