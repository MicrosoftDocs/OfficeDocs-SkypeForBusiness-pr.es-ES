---
title: Problemas conocidos de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: marcl
search.appverid: MET150
description: Lista actual de problemas conocidos en la aplicación cliente de Microsoft Teams y en la experiencia de los administradores.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ecafea114a38f857b56046c60504dd27c6617eb
ms.sourcegitcommit: 50dca374ef698dcdf787be815969be58f36562bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2018
ms.locfileid: "25784759"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conocidos de Microsoft Teams

En este artículo se enumera los problemas conocidos de Microsoft Teams, por área de característica.

## <a name="administration"></a>Administración

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los registros de auditoría pueden informar de un nombre de usuario incorrecto como iniciador cuando alguien se ha quitado de un equipo  <br/> |Equipo de los equipos es un grupo moderno en AAD. Cuando que agrega o quitar un miembro a través de la interfaz de usuario de los equipos, el flujo sabe exactamente el usuario que inició el cambio, y el registro de auditoría refleja la información correcta. Sin embargo, si un usuario de un miembro a través de AAD de agrega o quita, el cambio se sincroniza con el back-end de los equipos sin que indica que los equipos que inició la acción. Microsoft Teams recoge el primer propietario del equipo como el iniciador, que finalmente se refleja en así como el registro de auditoría.    <br/> |  <br/> |11/5/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Directiva EAF en el Kit de herramientas de la experiencia de mitigación mejorado (EMET) incorrectamente puede identificar las optimizaciones de espacio aislado de cromo como amenazas. <br/> |Hay un problema con espacio aislado de cromo en las que la directiva de exportación de dirección tabla acceso filtrado (EAF) en el Kit de herramientas de la experiencia de mitigación mejorado (EMET) y en Defender avanzada amenaza protección (ATP) de Windows puede identificar incorrectamente espacio aislado de cromo optimizaciones de como amenazas. Esto hace que los equipos no funcionen correctamente.  <br/> | Para evitar este problema, desactive EAF para los equipos. Puede leer más información sobre el problema [instrucciones de mitigaciones EMET](https://support.microsoft.com/en-us/help/2909257/emet-mitigations-guidelines) para obtener más información acerca de la directiva de Windows Defender ATP y EAF, vea [Customize aprovechan la protección](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection) <br/> |11/10/18 <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede agregar a miembros a los equipos cuando UsersPermissionToReadOtherUsersEnabled está establecido en false  <br/> |Cuando este valor está establecido en false en AAD, atención al cliente no puede agregar miembros interna y externa en Microsoft Teams, y se muestra el siguiente mensaje de error: "se no podríamos agregar miembros. Hemos ejecutado en un problema. Por favor, inténtelo de nuevo más tarde." Sin embargo, los miembros pueden agregarse directamente a los grupos de Office 365.    <br/> |Cambiar este valor en true en AAD.  <br/> |4/10/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Administración de administración de los conectores de todo el inquilino ya no está disponible  <br/> |Al intentar agregar un conector de cliente y versión en línea se produce el error: se produjo un error inesperado. Vuelva a intentarlo. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Deshabilitar con la configuración de los equipos. Vea el artículo de soporte técnicohttps://msdn.microsoft.com/microsoft-teams/connectors  <br/> |21/06/2017  <br/> |

## <a name="apps"></a>Aplicaciones

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Opciones de un conector falta para algunos equipos  <br/> |Cuando se hace clic con el botón derecho en un canal, la opción Conectores no aparece para ningún miembro del equipo.  <br/> |El usuario que cree el equipo debe tener un buzón en línea; de lo contrario, la opción Conector no estará disponible. Este es el comportamiento que se espera.  <br/> |26/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|"Asignaciones" aplicación permanece visible cuando deshabilitado  <br/> |Cuando la aplicación "Asignaciones" está deshabilitada en el centro de administración, sigue apareciendo en el cliente de los equipos de los usuarios con licencia EDU. Si lo selecciona cuando deshabilitado devolverá un error que indica, "Doh! Se produjo algún error..."  <br/> |No hay ninguna solución.  <br/> |29/12/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede eliminar los conectores como propietario de un equipo  <br/> |Si se intenta eliminar un conector como un propietario, que en caso contrario, puede agregar un conector, mientras "Permitir miembros para crear, actualizar y quitar conectores" está deshabilitada se produce un error que indica que el usuario no tiene permiso para hacerlo. <br/> |Habilitar temporalmente "Permitir miembros crear, actualizar y quitar conectores" le permitirá el propietario para eliminar el conector.  <br/> |27/7/18  <br/> |

## <a name="audio-conferencing"></a>Audioconferencia

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los autores de llamadas de RTC con el mismo "número de de" se muestran con el mismo usuario en la lista de participantes de la reunión.  <br/> |Cuando varios autores de llamadas de RTC unirse a una reunión, y sus identificadores de autor de la llamada se enmascaran como un solo número, se mostrará como un único autor de la llamada en la lista de reuniones.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Panel de información de la reunión no está visible forma intermitente.  <br/> |Panel de información de la reunión no se puede mostrar en el cliente de los equipos cuando los usuarios están intentando buscar para números de teléfono de puente de conferencia o identificador de conferencia.  <br/> |Examine los detalles de la reunión o el calendario de Outlook para ver los números de teléfono de puente de conferencia o identificador de conferencia.  <br/> |25/9/2017  <br/> |
|Invitaciones de reunión de Outlook, complemento mostrar caracteres de elementos no utilizados en las coordenadas de RTC para configuraciones regionales de EE.  <br/> |Al programar reuniones privadas mediante Outlook, complemento para Microsoft Teams en un equipo con configuraciones regionales que no sean-US, las coordenadas de RTC pueden contener caracteres de elementos no utilizados.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|En el marcado de las necesidades de uso de 5 dígitos o más.  <br/> |Los usuarios que intentan marcar un número de una reunión necesitan escribir 5 o más dígitos, aunque la regla de normalización del plan de marcado está disponible para normalizar el marcado de dígitos breve al formato E.164.  <br/> |Marcar un número, escriba el número DID completo o el formato de número local en lugar de número de extensión interna.  <br/> |25/9/2017  <br/> |
|Salida control no está visible forma intermitente.  <br/> |Salida control no estén visible en el panel de información de reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Identificador de conferencia estática no se admite para las reuniones de Microsoft Teams.  <br/> |Si el administrador reemplaza la configuración predeterminada de identificador de conferencia dinámico al identificador de conferencia estática, esta configuración no surtirán efecto para las reuniones de Microsoft Teams. Vea [uso de conferencias de Audio identificadores dinámicos en su organización](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Las coordenadas de la reunión de RTC no están disponibles para Skype local para usuarios de empresas  <br/> |Si el usuario es un Skype para usuarios de empresa local, asignado con Skype para profesionales en línea, conferencias de Audio y las licencias de los equipos, todas las reuniones programadas con los equipos no incluirá las coordenadas de la reunión de RTC. <br/> |No hay ninguna solución.  <br/> |1/2/2018  <br/> |

## <a name="authentication"></a>Autenticación

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando intenta unirse a Teams desde Internet Explorer o Edge, el programa lo intenta constantemente o se bloquea y no consigue iniciar sesión.   <br/> | Su organización utiliza los sitios de confianza de Internet Explorer y la aplicación basada en web de Teams no logra iniciar sesión correctamente porque los sitios de confianza de Teams no están permitidos. <br/>|Realice los siguientes cambios a la configuración de Internet Explorer o desde el Panel de Control, ya sea con derechos de administrador o un objeto de directiva de grupo:<br/><ol><li>En **Opciones de Internet** &gt; **Privacy** &gt; **Avanzadas**, Aceptar las cookies y de terceros y la casilla de verificación para **Permitir siempre las cookies de sesión**.</li><li>Haga clic en **Opciones de Internet** &gt; **seguridad** &gt; **Sitios de confianza** &gt; de **sitios**y agregar todos los elementos siguientes:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>NOTA</b>: Valide y permita siempre todas las direcciones URL de confianza de Teams y los requisitos del siguiente documento: [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Limitaciones de complementos de Outlook  <br/> |Para usar el complemento de Outlook, debe iniciar sesión en Microsoft Teams con la autenticación multifactor. Si se produce un error en la autenticación multifactor durante el proceso de inicio de sesión, podrá iniciar sesión en Microsoft Teams, pero recibirá un mensaje de error cuando intente usar el complemento.  <br/> Por el momento, el complemento solo está disponible para los usuarios de Windows.  <br/> El complemento no funcionará si usa un proxy de autenticación.  <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams siempre iniciará sesión en la cuenta de equipo unido a un dominio.   <br/> |Si un usuario tiene dos cuentas diferentes de los equipos y tiene una máquina con unido a dominio habilitado, los equipos usarán el perfil unido a un dominio en el equipo para el usuario iniciará sesión automáticamente en los equipos. Para cambiar a la otra cuenta de los equipos, el usuario debe cerrar la sesión de la aplicación y escriba las credenciales para la segunda cuenta para iniciar sesión manualmente. Si el usuario cierra sesión en los equipos y reinicie la máquina, al reiniciar, los equipos iniciará sesión automáticamente utilizando el perfil unido a un dominio. <br/> | No hay ninguna solución. <br/> |02/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Error de autenticación moderno - autenticación de formularios no está habilitado  <br/> |Cuando se produce un error inicial en la autenticación multifactor, use la aplicación web para la autenticación.  <br/> Para obtener más información, consulte [Servicios de federación de Active Directory prompt=login parameter support](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Comprobar esta configuración: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Organizador de compilación de inicio de sesión único (SSO) <br/> |El inicio de sesión único no se aplica en Planner. Tendrá que volver a iniciar sesión la primera vez que use Planner en cada cliente.  <br/> |No hay ninguna solución. Estamos trabajando en otras mejoras para la autenticación.  <br/> |28/02/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede guardar la imagen de perfil.  <br/> |Los usuarios no pueden guardar sus imágenes de perfil cuando el buzón de Exchange está hospedado (asignado) local en Exchange 2016 CU2 o inferior.  <br/> |No hay ninguna solución.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Explorador

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Aparecen anomalías verdes en las imágenes cuando se presenta un vídeo en Chrome.  <br/> |Artefactos verdes aparecen durante la visualización de vídeo o uso compartido de la pantalla en una llamada o meetup en cromo.  <br/> |Deshabilite la configuración de aceleración de hardware en Chrome.  <br/> |03/08/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Compatibilidad con el cliente web de Safari  <br/> |A los usuarios que intentan abrir el cliente web de Microsoft Teams en Safari se les redirige al sitio de descarga del cliente de escritorio. Microsoft está investigando la compatibilidad con Safari y compartirá las actualizaciones a través del [mapa de ruta de Microsoft Teams](https://aka.ms/TeamsRoadmap).  <br/> |Uso compatibles con exploradores de internet, que incluyen: Internet Explorer 11 +, Microsoft Edge 12 +, Chrome 51.0 + y Firefox 47.0 +.  <br/> |02/11/2016  <br/> |

## <a name="channels"></a>Canales

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cuando un usuario abandona la compañía, aparece en Microsoft Teams como "Usuario desconocido"<br/> |Cuando un usuario abandona la compañía, aparece en Microsoft Teams como "Usuario desconocido". Además, se muestra la ficha conversación: "usuario desconocido se ha agregado al equipo". <br/> |No hay ninguna solución.  <br/> |12/9/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden volver a crear un nombre de canal que haya existido anteriormente.  <br/> |Una vez que se crea el nombre de un canal, este no se puede volver a usar, incluso si se ha eliminado. Nuestro sistema mantiene estos datos para posibles situaciones de protección de información.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Cambio de nombre de un canal en Microsoft Teams no cambiar el nombre de la carpeta correspondiente en SharePoint Online  <br/> |Si se cambia el nombre de un canal en Microsoft Teams, no cambia la carpeta en la biblioteca de documentos de SharePoint Online correspondiente al equipo para que coincidan con. El nombre de carpeta de SharePoint Online correcto se muestra en la parte superior de la ficha archivos de canal cuyo nombre ha cambiado.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Vista previa de la dirección URL no puede mostrar para todos los de la dirección URL  <br/> |Algunos URL no puede mostrar una vista previa.  Esto depende de la dirección URL original tener la capacidad de mostrar una vista previa. <br/> |No hay ninguna solución. <br/> |9/1/18 <br/> |

## <a name="chat"></a>Chat

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Menciones @ para mensaje eliminado enviar notificación con vínculo de canal  <br/> |Hay una limitación conocida de notificación cuando esté en-que se mencionan en un mensaje que se elimina; se desplazará la notificación de la fuente para el canal, pero no para un mensaje específico. <br/> | Por diseño <br/> | 28/3/17  <br/>|


## <a name="client"></a>Cliente

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los equipos no se actualiza automáticamente   <br/> | Cuando se instala Microsoft Teams mediante secuencias de comandos de instalación en lugar de en la ubicación predeterminada, el cliente no actualización automática cuando estén disponibles nuevas versiones de archivos de programa.    <br/> | Por diseño. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`.  <br/> | 9/7/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Vínculo simbólico o mappying una unidad a C:\users hace que la aplicación debe iniciar pantalla en blanco  <br/> | Cuando se instala Microsoft Teams mediante secuencias de comandos de instalación en lugar de en la ubicación predeterminada, el cliente no actualización automática cuando estén disponibles nuevas versiones de archivos de programa.   <br/> | Por diseño. Asegúrese de instalar la aplicación en la ubicación predeterminada: `user\Appdata`. Si la asignación debe existir, debe usar la versión de web de Microsoft Teams.  <br/> | 9/7/17  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Vínculo simbólico o asignación de una unidad a c:\users hará que la aplicación debe iniciar pantalla en blanco  <br/> |Cuando la ubicación predeterminada de `C:\users\<user>\appData` se cambia desplazando el `C:\users` utilizando el vínculo simbólico o la carpeta, se iniciará la aplicación con una pantalla en blanco.   <br/> |No hay ningún trabajo conocido alrededor. Si la asignación debe existir, debe usar la versión de web de Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Entorno de

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los buzones de grupo no están habilitados para poder archivar en ellos (almacenamiento extra).  <br/> |En el Centro de seguridad y cumplimiento de Office 365, los administradores globales no pueden habilitar el archivado en los buzones de grupo. Solo pueden hacerlo en los buzones de los usuarios.  <br/> |Si la capacidad del buzón de grupo está casi llena, póngase en contacto con el soporte técnico de Microsoft Office para ampliar el tamaño del buzón.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Acceso de invitado

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los clientes de la UE y APAC reciben un error cuando agregan un usuario invitado desde otro inquilino    <br/> | Los clientes de la UE y APAC sufren un retraso en la replicación entre Microsoft Teams y Azure Active Directory. Cuando un usuario de un inquilino de UE o APAC intenta agregar un usuario invitado desde otro inquilino, recibe un mensaje de error indicando que vuelva a intentarlo.   <br/> |Haga clic en el botón para reintentar y vuelva a realizar la adición del usuario invitado.  <br/> |08/11/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se ha creado una wiki para los canales que creen los invitados.  <br/> |Cuando un invitado crea un canal, no se crea la ficha **Wiki**. La ficha **Wiki** no se puede adjuntar manualmente al canal. <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

## <a name="meetings"></a>Reuniones.

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden tener acceso a las reuniones o conectores pero tienen buzones de Exchange Online. <br/> |Cliente activamente bloquea EWS desde servicios dentro de Exchange Online, pero necesita tener MS Teams compatible con dentro de las directivas de EWS. <br/> |Para hacer que MS Teams compatible, debe agregar la siguiente cadena de agente de usuario para MS Teams dentro de la EWSAllowList: `*skypespaces*`, incluidos los asteriscos. El comando completo es:`set-organizationconfig -ewsallowlist *skypespaces*`<br/> Para obtener más información:https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps <br/> |30/5/17  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se necesita Skype Empresarial para algunas reuniones.  <br/> |Para su comodidad, su calendario de citas se muestra en Microsoft Teams. Para entrar en una reunión, solo tiene que hacer clic en el botón **Unirse**. <br/> Mientras trabajamos para seguir desarrollando esta área, si esta reunión se programó con Skype Empresarial, cuando haga clic en **Unirse**, Microsoft Teams iniciará su cliente de Skype Empresarial para que pueda terminar de entrar en la reunión. Las reuniones que se programaron en Microsoft Teams se iniciarán directamente en este producto.  <br/> En el futuro, simplificaremos esta experiencia.  <br/> |Haga clic en **Unirse**. Microsoft Teams decidirá de manera inteligente si es necesario Skype Empresarial para que un usuario se una a la reunión en función de la dirección URL que se ha incluido en la descripción de la reunión.  <br/> |13/03/2017  <br/> |


|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Número máximo de asistentes para las reuniones  <br/> |Cada reunión de Microsoft Teams puede albergar un máximo de 80 asistentes.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las reuniones no están disponibles.  <br/> |La funcionalidad de la reunión no está disponible cuando el buzón de Exchange esté hospedado (asignado) local en la versión menor que Exchange 2016 CU3.  <br/> |Actualice a la actualización acumulada 3 de Exchange 2016 o posterior para la implementación local.  <br/> |28/02/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No hay audio al uso compartido de contenido durante una reunión de difusión  <br/> |Cuando no se puede compartir contenido durante una reunión de difusión, audio desde el contenido compartido (vínculo de youtube o un archivo de vídeo guardado) escuchar por los participantes.  <br/> |Ninguno como esto es así por diseño.  Actualmente, los equipos no admite el uso compartido de contenido de audio  <br/> |9/10/18  <br/> |

## <a name="mobile"></a>Móvil

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No puede ver canales automático favoritos  <br/> |Algunos miembros no pueden ver los canales automático favoritos en la aplicación móvil.  <br/> |Miembros deben iniciar sesión en la aplicación web o de escritorio en primer lugar para ver canales automático favoritos en su aplicación móvil.  <br/> |30/4/18  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |Es posible que los usuarios no puedan cambiar de cuenta en dispositivos móviles administrados por Intune.  <br/> |No hay ninguna solución.  <br/> |20/09/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|No se puede usar divertida selector o Giphys o pegatinas en aplicación móvil  <br/> |No puede usar archivos GIF, emojis o pegatinas en los clientes móviles.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Diferencias de diseño de los equipos cliente móvil  <br/> |Los equipos se muestran en orden alfabético y no se puede contraer los canales en el cliente móvil.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|


## <a name="people"></a>Personas

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Fotos de perfiles de usuario  <br/> | Actualmente los equipos no tiene un mecanismo para impedir que los usuarios cambien las fotos. El equipo de BTS ha satisfecho con el equipo de desarrollo que se archivó lo siguiente para consideración: característica 108874: directiva de TI para deshabilitar la carga de fotos de perfiles   <br/> | Si dispone de los clientes que desean la capacidad para impedir la carga de fotos de perfiles en los equipos, por favor, solicite que agreguen su caso voto y empresarial a comentarios aquí:https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos
 <br/> |1/3/17 <br/> |

## <a name="provisioning"></a>Aprovisionamiento

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Se ha creado un usuario de SharePoint incorrecto para el sitio de SharePoint en Microsoft Teams.  <br/> |El administrador de SharePoint aparece como el creador de SharePoint para un grupo de Microsoft Teams, en lugar del usuario correcto.  <br/> Cuando se realiza una auditoría desde la consola de administración de SharePoint, el creador de la página de colección de sitios asociada con el grupo de Office 365 que se crea con el equipo de Microsoft Teams es el administrador de SharePoint.  <br/> |No hay ninguna solución.  <br/> |21/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los usuarios no pueden crear un equipo.  <br/> |Es posible que su empresa haya establecido una directiva para restringir quién puede crear equipos o grupos de Office 365.  <br/> |Compruébelo con su administrador de TI para saber cuál es la directiva de su empresa en relación con la creación de grupos y equipos.  <br/> |13/03/2017  <br/> |

## <a name="tabs"></a>Fichas

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Ficha sitio Web conduce a confusión en el cliente  <br/> |Las fichas del sitio Web no son equivalentes a su explorador. Un número de sitios, sobre todo aquellas que requieren autenticación o uso de elementos emergentes, no funcionará cuando anclados como una ficha de sitio Web.  <br/> |Estamos trabajando en la mejora de la interfaz de usuario para que sea más clara para los clientes.  <br/> |5/2/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Fichas no funciona desde que se habilitó acceso condicional <br/> |Algunas fichas no pueden cargarse ya en el cliente de escritorio desde que se habilitó acceso condicional en el inquilino. Cuando se usa al cliente Web de carga de las fichas. Algunas fichas que podrían verse afectados son: PowerBI, formularios, VSTS, PowerApps y lista de SharePoint.  <br/> |Para ver las fichas afectadas debe usar los equipos en perimetral, Internet Explorer o Chrome con la extensión de las cuentas de Windows 10 instalada. Algunas fichas todavía dependen de la autenticación web, que no funciona en el cliente de escritorio cuando está habilitada la entidad emisora de certificados. Trabajamos con socios para habilitar estos escenarios; hasta ahora hemos habilitado organizador, OneNote y Stream. <br/> |4/5/18  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de espacios de trabajo no está ordenada alfabéticamente.  <br/> |Los usuarios que tienen que cambiar de espacio de trabajo cuando agregan una ficha PowerBI verán que la lista de espacios de trabajo entre los que tienen que alternar no está ordenada alfabéticamente.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La barra de desplazamiento desaparece cuando se seleccionan informes.  <br/> |Cuando los usuarios que agregan informes de PowerBI intentan desplazarse por una lista que es más extensa que la pantalla de los informes no pueden evitar que se pierda la barra de desplazamiento.  <br/> |Use la flecha arriba o la flecha abajo para desplazarse por la lista.  <br/> |13/03/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los equipos de la integración de organizador con organizador en línea <br/> |Cubos de tareas en el organizador no se muestran en la experiencia en línea del organizador.  <br/> |No hay ninguna solución. <br/> |28/02/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Ficha de la página de SharePoint representa una pantalla en blanco<br/> |SharePoint Online dominios de cortesía actualmente no son compatibles. La experiencia del usuario es una pantalla en blanco cuando attemting para agregar una SharePoint ficha de página. <br/> |No hay ninguna solución. <br/> |20/8/18  <br/>|

## <a name="teams"></a>Microsoft Teams

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los registros de auditoría pueden informar de un nombre de usuario incorrecto como iniciador cuando alguien se ha quitado de un equipo  <br/> |Equipo de los equipos es un grupo moderno en AAD. Cuando que agrega o quitar un miembro a través de la interfaz de usuario de los equipos, el flujo sabe exactamente el usuario que inició el cambio, y el registro de auditoría refleja la información correcta. Sin embargo, si un usuario de un miembro a través de AAD de agrega o quita, el cambio se sincroniza con el back-end de los equipos sin que indica que los equipos que inició la acción. Microsoft Teams recoge el primer propietario del equipo como el iniciador, que finalmente se refleja en así como el registro de auditoría.    <br/> |  <br/> |11/5/18  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La carga de fotos en Teams no está bloqueada en OWA/Outlook como requiere la directiva   <br/> | Teams permite a los usuarios cargar fotos directamente en Office 365, a pesar de la configuración de la directiva que hay en vigor para evitar que se carguen fotos en OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|La lista de equipos públicos no incluye a todos los equipos.  <br/> |La lista de equipos públicos está basada en Microsoft Graph.  <br/> |Si no ve un equipo, pruebe a buscarlo en el cuadro de la parte superior derecha. Además, los propietarios de equipo deben comunicar nombres de equipo a compañeros ya que podrían mostrar muchos equipos de copia de seguridad en los resultados de búsqueda. <br/> | 21/07/2017  <br/>|

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Nombres de equipo que contienen caracteres especiales pueden crear errores de creación de la reunión  <br/> |Usuario recibirá el mensaje de **error se ha producido** en rojo al intentar crear una reunión de un equipo que tenga caracteres especiales en el nombre.   <br/> |Cambiar el nombre o vuelva a crear equipo con un nombre que no contenga un "/".  <br/> |13/07/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El nombre de un equipo con un &amp; símbolo en ella saltos de funcionalidad de conector  <br/> |Cuando se crea un nombre de equipo e incluye el símbolo &amp;, no pueden establecerse los conectores dentro del equipo/grupo.  <br/> |No se deben usar caracteres especiales en los nombres de equipo.  <br/> |21/06/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|El límite máximo de miembros de un equipo es 2500.  <br/> |Cada equipo de Microsoft Teams puede incluir un máximo de 2500 miembros por equipo.  <br/> |No hay ninguna solución.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Al eliminar un equipo, también se elimina el grupo que está asociado a él.  <br/> |Es posible que los usuarios no se percaten de que el grupo de Office 365 subyacente se elimina cuando se elimina el equipo. Además, si se elimina el grupo de Office 365 subyacente, el equipo se elimina también.  <br/> |Un idioma adicional en Microsoft Teams proporciona esta información al usuario. Esta información no está presente en la interfaz de grupos de Office 365. El departamento de soporte puede recuperar un grupo eliminado o equipo.  <br/> |13/03/2017  <br/> |

|**Título del problema**|**Comportamiento/síntoma**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Aplicación de escritorio de los equipos que muestra la pantalla en blanco  <br/> | <br/> |Intente eliminar o volver a instalar a los controladores de gráficos en el equipo o iniciar los equipos desde una línea de comandos con una marca GPU deshabilitar:<ul><li>Para Windows: Abra el símbolo del sistema y escriba lo siguiente:`cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Terminal para Mac: Inicio y escriba lo siguiente:`cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

