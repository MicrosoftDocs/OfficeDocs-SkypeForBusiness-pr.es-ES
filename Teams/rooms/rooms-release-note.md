---
title: Notas de la versión para Salas de Microsoft Teams (Windows)
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: El administrador puede leer las notas de la versión de Salas de Microsoft Teams, que muestran mejoras acumulativas en Salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f91c286f08046d1a521d3758f1fc297bf2aa0d59
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187026"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notas de la versión para Salas de Microsoft Teams

En este artículo se describen las mejoras acumulativas de Salas de Microsoft Teams.

Hay dos tipos de actualizaciones para Salas de Teams: Salas de Teams actualizaciones de aplicaciones y Teams cliente web. 

Salas de Teams las actualizaciones de las aplicaciones se realizan mediante el Microsoft Store o a través de [la actualización manual](manual-update.md). Esto actualiza la aplicación de Plataforma universal de Windows (UWP) que se instala localmente en el dispositivo.

Teams las actualizaciones del cliente web se realizan a través de los servicios de entrega de aplicaciones web de Teams. Se trata de un servicio basado en la nube que no requiere una actualización de la aplicación local para UWP instalada en el dispositivo.

Para obtener más información sobre cómo Teams actualizaciones, consulta [Teams proceso de actualización](../teams-client-update.md)

Salas de Teams se rige por la directiva moderna de ciclo de vida. Consulte [Teams proceso de actualización](../teams-client-update.md#servicing-agreement) para obtener más información.

## <a name="version-history"></a>Historial de versiones

|Lanzamiento |Publicado en <br/> Microsoft Store |
|--- |--- |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web-Client versión | Diciembre de 2021 |
|Teams Web-Client versión | Octubre de 2021 |
|4.10.10.0 |10/1/2021 |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Salas de Microsoft Teams introducción a la característica y resolución de problemas

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introducido en esta actualización:
- Los administradores de TI pueden inscribir un dispositivo de salas de Teams para recibir características de vista previa pública a través de la configuración XML. Una vez inscrito, el dispositivo comenzará a recibir características beta. Todas las características que van a las pruebas beta se anuncian en [Microsoft Teams versión preliminar pública: Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- El administrador de TI puede establecer la resolución de pantalla frontal de la sala y escalar de forma remota a través de la configuración <sup>XML2</sup>
- El administrador de TI puede deshabilitar la supresión de ruido de Microsoft mediante la configuración <sup>XML3</sup> 
- El administrador de TI puede invalidar la limpieza de la carpeta de descarga en el dispositivo mediante la configuración de la clave del <sup>Registro4</sup>
- Permitir a los usuarios unirse a Teams reunión hospedada en otra nube (es decir, el cliente de GCCH puede unirse a reuniones de Teams hospedadas en la nube comercial y viceversa) 
- Teams salas bloquea el inicio del explorador edge desde las direcciones URL de PowerPoint Live como medida de seguridad adicional para las salas de Teams con pantallas táctiles. 
- La experiencia Reunirse ahora se ha mejorado para agregar instrucciones para que los usuarios inviten a usuarios a la sala 
- Compatibilidad con Windows 10 versión de características 21H2 para salas Teams   
- Nuevo Cortana punto de entrada en la pantalla de inicio, el botón Compartir/presentar vuelve 

> <sup>1</sup> Puedes encontrar instrucciones para inscribir la versión preliminar pública de mtr Windows dispositivos [aquí](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> La resolución de pantalla frontal de la sala y el escalado remoto a través de XML se pueden encontrar [aquí](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> En este momento, solo se está publicando la configuración de administrador. El control del usuario y la habilitación de la supresión del ruido seguirán a la publicación 4.12 en mayo de 2022. 
>
> <sup>4</sup> Puedes encontrar instrucciones de limpieza de dispositivos [aquí](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 actualización de características de 21H2 se actualizará después de 7 días desde la instalación de la aplicación o los administradores pueden usar la actualización manual en su lugar para instalar más rápido. Salas de Microsoft Teams versión 4.12 de la aplicación con estos cambios, comenzará a implementarse en abril de 2022 y finalizará el lanzamiento entre 2 y 3 semanas. Las actualizaciones de la aplicación se entregan a través de Windows store y la aplicación se instala automáticamente. Esto se está implementando solo en Salas de Microsoft Teams en Windows. Lo que tiene que hacer para prepararse: es posible que desee notificar a los usuarios sobre esta experiencia actualizada y actualizar su formación y documentación según corresponda.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introducido en esta actualización:
- Corrección de errores para el encuadre de la cámara, que mejorará todo el contenido de la vista de la cámara.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introducido en esta actualización:
- Diseño fila frontal (vista previa) para MTR en Windows <sup>1</sup> 
- Configuración de administración para establecer el diseño de fila frontal como predeterminado  
- Reunirse ahora y llamar a la actualización de la aplicación solo para Teams, Teams modos de cliente <sup>predeterminados1,2</sup>
- Cambiar entre varias cámaras de vídeo en Teams <sup>reuniones1</sup> 
- Configuración predeterminada de la cámara de vídeo 
- Cortana actualización de iconos push-to-talk en la consola MTR 
- Inclusión de licencias de Azure AD Premium 1 en room standard y SKU de Premium 
- AAD compatibilidad de directivas de acceso <sup>condicional3</sup> 
- Cortana activación por voz habilitada de forma predeterminada en la OOBE
- Compatibilidad con controles PTZ <sup>remotos4</sup>

> <sup>1</sup> Estas características se están implementando con Teams cliente web y se implementarán en las próximas semanas. Más información sobre [las actualizaciones de Teams](../teams-client-update.md) para obtener más información.
> 
> <sup>2</sup> salas Teams de Windows que se ejecutan solo en Microsoft Teams o Skype Empresarial y Microsoft Teams (predeterminado) se actualizan con las nuevas experiencias de reunión y llamada, pero otros modos no se ven afectados por esta actualización.
> 
> <sup>3</sup> Vea los detalles adicionales sobre cómo configurar AAD directivas de [acceso condicional](../rooms/rooms-authentication.md#azure-ad-conditional-access) para Salas de Teams.
> 
> <sup>4</sup> Esta característica requiere que los administradores de TI configuren Teams aplicación de controles PTZ remotos del cliente de escritorio.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Salas de Teams actualización del cliente web (diciembre de 2021)

Introducido en esta actualización:
- El diseño de vídeo dividido en la parte frontal dual de la sala se muestra cuando no se comparte el contenido

### <a name="teams-rooms-web-client-update-october-2021"></a>Salas de Teams actualización del cliente web (octubre de 2021)

Introducido en esta actualización:
- Control de lista unificado con Teams cliente de escritorio con agrupación de reuniones estructuradas, opciones de reunión y controles para moderadores/asistentes, criterio de ordenación de la mano y capacidad para invitar a usuarios desde chat o invitación de reunión directamente desde la lista 
- Alineación de los controles de llamada de barra universal con el cliente de escritorio en los controles de llamada de reunión, el botón Diseño y la información de estado de la reunión
- Compatibilidad dinámica con la galería para pantallas frontales de sala individuales y dobles
- Selector de diseño unificado para la opción de diseño de sala consolidada
- Destacar o anclar a varios participantes en Teams reuniones
- Las reuniones grandes admiten controles de moderador/asistentes accesibles pulsando participantes de la lista
- Posibilidad de bloquear una reunión para las reuniones donde la sala sea organizador, así como conciencia de que la reunión está bloqueada
- Compatibilidad con el consumo del modo Moderador (hombre del tiempo) cuando un usuario remoto comparte contenido con la opción de vista Moderador
- Soporte de reacciones en reuniones de Teams 

> [!NOTE]
> Las actualizaciones del cliente web están disponibles para todos los Salas de Teams con las versiones de la aplicación 4.10 y 4.9. Los administradores podrán inscribirse en Salas de Teams programa de vista previa pública para obtener pronto un vistazo a las características del cliente web.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introducido en esta actualización:
- El mando a distancia de la sala permite a los usuarios controlar la funcionalidad básica de la sala mediante Teams en su móvil *
- Soporte de cámara de contenido logitech scribe para el botón BLE para compartir en una reunión
- Las burbujas de chat proporcionan notificaciones en el chat de la reunión para llamar la atención sobre lo que se dice mediante el chat de la reunión *
- La galería grande y la compatibilidad con el modo conferencia ya están disponibles en GCC Alto
- Nuevas habilidades agregadas a Cortana, Agregar persona por nombre a la reunión y Llamar por nombre 
- Cortana La opción Pulsar para hablar está habilitada de forma predeterminada en todos los dispositivos. Para obtener más información, consulta [Cortana asistencia por voz en Teams](../cortana-in-teams.md).

> [!NOTE]
> Soporte técnico 19H1 obsoleto. La versión mínima del sistema operativo compatible con 4.10 es 19H2.

> [!NOTE]
> *Estas características se implementan con Teams servicio y funcionarán con todas las versiones de aplicación superiores a 4.9.

> [!NOTE]
> Para unirse a la reunión programada, tanto desde Teams aplicación móvil como desde MTR-W, busque la cuenta de sala en la lista de la aplicación Teams Mobile y pulse el menú "Controlar este salón" y puede controlar los controles de llamada desde la aplicación.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introducido en esta actualización:
- Microsoft Teams modo solo está ahora disponible en la configuración de la aplicación, por lo que ya no es necesario configurar una cuenta de Skype Empresarial. En este modo, los dispositivos que han iniciado sesión en Teams solo se unen a las reuniones Skype Empresarial como usuario invitado.
- Corrección para el audio HDMI que causa un volumen de llamada menor. La característica de audio HDMI se habilita automáticamente para todos los dispositivos con la compilación de la aplicación 4.9.12.0.

> [!NOTE]
> Con Skype Empresarial llegando al final de su vida útil, se recomienda actualizar al modo solo Teams.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introducido en esta actualización:
- soporte técnico de Windows 10 20H2 

> [!NOTE]
> Crestron UC-Engine (fecha de versión del BIOS que contiene "KYSKLi") Salas de Teams tienen problemas de compatibilidad y los oem de sistema proporcionarán controladores actualizados en un futuro próximo. Windows 10 20H2 no se ofrecerá a estos dispositivos. Para obtener más información sobre Windows compatibilidad de versiones, consulta [Windows 10 soporte técnico de versiones](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introducido en esta actualización:
- Se ha corregido un problema por el que la información de sala en las consolas de Salas de Teams no se mostraba para las cuentas de sala ocultas de la lista global de direcciones (GAL)

> [!NOTE]
> Los clientes de GCCH pueden descargar el paquete de actualización desde [Actualizar manualmente un dispositivo Salas de Microsoft Teams](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introducido en esta actualización:
- compatibilidad con Government Community Cloud High (GCCH) para Salas de Teams. Los clientes de GCCH con dispositivos Salas de Teams existentes pueden descargar la versión 4.8.19.0 desde [Actualizar manualmente un dispositivo Salas de Microsoft Teams](manual-update.md)
- Únase a reuniones de Zoom con una mejor calidad de vídeo (compatibilidad con 720p) y reciba la galería de vídeos de los participantes
- Skype Empresarial banner de error de inicio de sesión eliminado para Teams modo predeterminado. Este cambio permite a las organizaciones quitar Skype Empresarial infraestructura
- Teams el análisis de vínculos para unirse a reuniones ahora controla la Protección contra amenazas avanzada de Microsoft Defender Caja fuerte Vínculos para permitir unirse a Teams externos sin problemas
- Corrección del problema de escalado de contenido compartido en reuniones de Skype Empresarial cuando el equipo del participante tiene un valor de PPP personalizado establecido en Windows
- Correcciones de calidad y confiabilidad

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introducido en esta actualización:
- Correcciones de calidad y confiabilidad

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introducido en esta actualización:

- Compartir audio HDMI con los participantes de la reunión en Teams reunión
- Cortana habilidades de voz (vista previa)
- Evite el audio activado en función de los permisos de audio cuando Salas de Teams se una como asistente. Para obtener más información, vea [Administrar los permisos de audio de los asistentes en reuniones de Teams](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Destacar el vídeo de alguien desde Teams consola de sala y consumir vídeo destacado en pantallas de salas

> [!NOTE]
> Cortana habilidades de voz están disponibles para periféricos de audio seleccionados para inquilinos ubicados en la Estados Unidos. En el futuro se agregarán más países o regiones. Para obtener más información, consulte [Cortana asistencia por voz en Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introducido en esta actualización:

- Corrección de la media pantalla blanca al invocar el teclado en pantalla en Teams reunión

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introducido en esta actualización:

- Ver más vídeos con la galería de vídeos de 3x3 delante de las pantallas de sala  
- Iniciar subtítulos locales en directo desde MTR
- Unirse a reuniones de Zoom desde Salas de Teams con unirse invitado directo (vista previa)

> [!NOTE]
> La galería de vídeo de 3x3 y los subtítulos locales en directo se entregan a través del servicio de Microsoft Teams. Estas características están disponibles para todos los dispositivos Salas de Teams con la versión de aplicación 4.5.37.0 y posteriores.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introducido en esta actualización:

- Reuniones coordinadas entre Microsoft Teams y Surface Hub 2S
- Corrección del error de inicio de sesión de Skype Empresarial al [instalar Windows 10 actualización KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) o [Windows 10 actualización KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introducido en esta actualización:

- Unirse a reuniones WebEx de Cisco desde Salas de Teams con unirse invitado directo
- Teams habilitación y la inscripción automática del Centro de administración
- Soporte técnico de la versión Windows 10 1909
- Cambiar al diseño de la galería de vídeos incluso cuando el contenido está presente
- Apoyo para levantar la mano virtual para el asistente y controles para el moderador
- Configuración de volumen predeterminada ajustable para conferencia y altavoz predeterminado
- Buscar y llamar a usuarios federados (inquilino) desde Teams Room

> [!IMPORTANT]
> La versión 4.5 es la última versión para admitir Windows 10 versión 1803; las versiones futuras no se ofrecerán a los sistemas en Windows 10 versión 1803. Para obtener más información sobre Windows compatibilidad de versiones, consulta [Windows 10 soporte técnico de versiones](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introducido en esta actualización:

- Correcciones de calidad y confiabilidad
- Corrección del problema "la aplicación no se inicia después de actualizar a 4.4.41.0"

> [!NOTE]
> Si el dispositivo no se actualiza automáticamente a la versión 4.4.63.0, sigue los pasos de [Salas de Microsoft Teams aplicación no se inicia después de actualizar a la versión 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) para resolver el problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introducido en esta actualización:

- Correcciones de confiabilidad para el inicio de aplicaciones en el quiosco de Windows 10

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introducido en esta actualización:

- Compatibilidad de autenticación moderna para Exchange y Skype Empresarial
- Compatibilidad con llamadas de emergencia dinámicas para Teams (componentes de servicio necesarios y distribuidos mediante anillos de cliente Teams)
- Capacidad para deshabilitar el contenido duplicado fuera de la reunión para salas de doble visualización con XML
- Pantalla de presentación de aplicaciones
- Avisos de software de código abierto (OSS) en la configuración del dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introducido en esta actualización:

- Actualizaciones de directivas para "actualizaciones de Windows para empresas"
- Corrección de los informes de eventos de dispositivo que muestran un error en Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introducido en esta actualización:

- Corrección de un problema de cambio de tamaño o parpadeo de Windows que se observa en determinadas configuraciones
- Procesamiento del calendario para reuniones de terceros quitadas
- Cortana configuración de estado quitada

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introducido en esta actualización:

- Respuesta automática a llamadas basadas en proximidad y configuración de administrador para controlar esto
- Actualización de la interfaz de usuario Configuración administración de dispositivos con la adición de la configuración del dispositivo en la pestaña Acerca de
- Control de sala volver a la pantalla principal
- SKU de Sala de reuniones disponible en GCC
- Compatibilidad con la cámara de contenido para el sistema basado en Surface Pro (compilación mínima necesaria de la aplicación: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introducido en esta actualización:

- soporte técnico de Windows 10 1903. Windows 10 actualización de 1903 se ofrece en unos días después de la actualización de la aplicación
- Las correcciones para el teclado en pantalla no se muestran confiablemente

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introducido en esta actualización:

- Una nueva característica de cámara de contenido que permite a los usuarios incluir de forma inteligente una pizarra tradicional en su Teams reunión
- Mejoras adicionales en la interfaz de usuario de la consola para reducir el desorden y movido Configuración a una nueva barra lateral a la que se accede a través de Más en la consola
- Botón Compartir bandeja deshabilitado si el cable de contenido local no está conectado o si no hay una cámara de contenido conectada
- Se ha corregido un problema con el teclado táctil que provocaba que no apareciera por primera vez después de reiniciar el sistema MTR.
- Correcciones de calidad y confiabilidad

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introducido en esta actualización:

- Skype aplicación de la tienda room system rebrand to "Salas de Microsoft Teams"
- Salas de Microsoft Teams interfaz de usuario de la consola vuelve a alinearse con Microsoft Teams
- Actualización del tema: mantenga solo la imagen de fondo personalizada delante de las pantallas de la sala, mientras convierte el fondo de la consola en un color neutro para garantizar que los controles de la interfaz de usuario de la consola cumplan con el contraste de color( requisitos de accesibilidad
- Barra universal para los controles de llamada en la reunión de Teams llamadas o reuniones con el fin de proporcionar una experiencia coherente con Microsoft Teams PC/ web/ clientes <sup>móviles1</sup>
- Calificación de los comentarios sobre la calidad de las llamadas después de Teams llamadas o <sup>reuniones1</sup>
- Recibir o representar Microsoft Whiteboard en Salas de Microsoft Teams frente a la pantalla de la sala cuando se comparte desde PC/ Web/ Mobile Teams <sup>cliente1</sup> <sup>2</sup>
- Se ha quitado la compatibilidad con las actualizaciones de Windows 10 versión 1809 debido a problemas de compatibilidad con Salas de Microsoft Teams cliente. Windows 10 compatibilidad con la versión 19H1 se agregará en futuras versiones

<sup>1</sup> Microsoft Teams implementación del servicio con anillos de Teams. Es posible que esta característica esté disponible antes o después de la actualización del cliente 4.0.105.0

<sup>2</sup> Requiere que los administradores de TI activen Microsoft Whiteboard. Además, si tiene una pantalla táctil frontal de la sala, debe calibrar varias pantallas táctiles mediante la configuración de Windows con el inicio de sesión del administrador del dispositivo para empezar a usar Microsoft Whiteboard para la colaboración desde una pantalla compartida en una reunión de Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introducido en esta actualización:

- Corrige un problema con la característica "enviar comentarios"
- Optimizaciones en preparación para la próxima actualización de Salas de Microsoft Teams dispositivo a Windows 10 versión 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introducido en esta actualización:

- Corrección del error "cuelgue en el inicio de la aplicación" que afectaba a los dispositivos en la compilación RS2 Windows 10 heredada.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introducido en esta actualización:

- Teclado DTMF para Microsoft Teams reuniones P2P y llamadas RTC. Para que Microsoft Teams el cliente de llamadas predeterminado, los administradores deben establecer IsTeamsDefaultClient en true
- Ancle el vídeo entrante de un participante remoto a pantalla completa delante de la pantalla de la sala. Usar el comando "Anclar" de la lista de participantes en la consola
- Mejoras en las notificaciones de la sala de espera con la adición de notificaciones de delante de la sala
- El icono de proyección frontal de la sala se quita cuando la baliza de Bluetooth no está habilitada en Salas de Microsoft Teams dispositivo
- Corrección del problema de control de volumen en reuniones de Teams

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introducido en esta actualización:

- Mostrar contenido en ambas pantallas frontales de la sala (FoR) en sistemas de salas de doble pantalla
- Mejoras en la interfaz de usuario de Los documentos y frente a la sala
- Compatibilidad con TLS 1.2 del lado del cliente. Para los clientes locales, habilitar la comunicación a través de TLS 1.2 para Salas de Microsoft Teams requiere la actualización acumulativa 9 (CU9) de Skype Empresarial Server 2015 o Skype Empresarial Server actualización acumulativa 1 (CU1) de Skype Empresarial Server 2019.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introducido en esta actualización:

- Compatibilidad con pantalla dual (delante de la sala) para reuniones de Teams

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introducido en esta actualización:

- Correcciones de calidad y confiabilidad

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introducido en esta actualización:

- Cambios de código necesarios para preparar la aplicación Salas de Microsoft Teams para una actualización posterior Windows 10 versión 1803
- Corregir el problema de formato con EULAs localizados (específicamente noruego) que impide avanzar más allá de la ventana de configuración de EULA OOBE
- Se necesitan cambios de código para que Salas de Microsoft Teams aplicación se ejecute en sistemas de salas de Lync heredados. Puedes ver más [aquí](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introducido en esta actualización:

- Revisión de la aplicación Crestron no se inicia, lo que normalmente sería accesible cuando se presiona el botón de la aplicación en un dispositivo Crestron SR. Salas de Microsoft Teams es necesario reiniciar la aplicación después de la instalación de 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introducido en esta actualización:

- Mejoras de características de "Informar de un problema" en el modo Teams (equivalente a "Enviar comentarios" en modo Skype Empresarial)
- Habilitar la posibilidad de retroceder de Teams al modo Skype Empresarial para llamadas SIP
- Mejoras de accesibilidad (Narrador, Lupa)
- Reiniciar automáticamente la aplicación cuando sea necesario después de aplicar los cambios de aprovisionamiento XML
- Varias correcciones

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introducido en esta actualización:

- Esta actualización permite la compatibilidad de reuniones Skype Empresarial *y* Teams en dispositivos room systems. Teams está desactivada de forma predeterminada una vez que se aplica la actualización. Los administradores pueden habilitar Teams localmente en la configuración del dispositivo o mediante una inserción xml remota.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introducido en esta actualización:

- Se corrige el error de dirección detectado en algunos sistemas durante el inicio de la aplicación.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introducido en esta actualización:

- Cambios que permiten a Microsoft administrar de forma más flexible las actualizaciones de Windows.
- No hay cambios en la experiencia del usuario final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introducido en esta actualización:

- Corrección para solucionar los problemas de respuesta de la consola observados en dispositivos basados en Surface Pro 2017 conectados a dos pantallas frontales de la sala y la entrada de vídeo
- Comprobación automatizada para asegurarse de que el sistema ejecuta el script de aprovisionamiento más reciente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introducido en esta actualización:

- Corrección para mejorar el comportamiento de OSK (teclado en pantalla) en sistemas basados en Windows 10, versión 1709
- Mejoras para prepararse para futuras actualizaciones del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introducido en esta actualización:

- Aplicación actualizada para mejorar la telemetría

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introducido en esta actualización:

- Corrige un problema que provocaba que se presentara un problema intermitente al unirse a la reunión
- Corrige un problema conocido que provocaba una experiencia de "bloqueo" del dispositivo.

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introducido en esta actualización:

- Correcciones de errores o bloqueos para mejorar la estabilidad
- Compatibilidad con consola de tamaño variable
- Descarga de procesamiento de audio periférico (lista de permitidos multimedia adicional)
- Optimizaciones que permiten a los profesionales de TI crear imágenes para ti mismo con Windows 10 actualización de enero de la versión 1709 y posteriores.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introducido en esta actualización:

- Corrige un problema con la característica "Enviar comentarios".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introducido en esta actualización:

- Compatibilidad con hardware de base [polycom serie MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Soporte técnico para [Logitech Brio](https://www.logitech.com/product/brio)
- Se resuelve un problema por el que las pantallas (consola y parte frontal de la sala) no entran en el modo de suspensión cuando no hay actividad en la sala

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introducido en esta actualización:

- Se ejecuta en una tableta con Surface Pro (2017)
- Es compatible con Windows 10 Enterprise Creators Update (idioma inglés, compilación 1703)
- Compatibilidad con hardware de base [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Compatibilidad de OEM para controles de entorno (Crestron)

La versión de 64 bits de Windows 10 Enterprise Edición de aniversario (idioma inglés, versión 1607) ya no es compatible con Salas de Microsoft Teams versión 3.0.12.0 (actualización 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introducido en esta actualización:

- Resuelve los problemas observados al buscar usuarios federados a través del campo de búsqueda Participantes. Antes de esta corrección, es posible que los resultados de búsqueda de los usuarios federados externos no se hayan resuelto correctamente y, en su lugar, hayan devuelto resultados incorrectos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introducido en esta actualización:

- Dual-Screen soporte técnico (para la paridad del sistema heredada)
- Temas (temas integrados y la capacidad de establecer temas personalizados)
- Capacidad de enviar comentarios sobre compilaciones públicas
- Telemetría mejorada en relación con la confiabilidad de la unión a reuniones
- Informes de OMS mejorados
- Posibilidad de que el administrador de TI configure dispositivos de forma remota

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introducido en esta actualización:

- Selección por parte del usuario desde la aplicación de dispositivos USB de audio y vídeo de la sala de reuniones
- Informes de estado de la consola de sala integrada para los clientes que usan Microsoft Operations Management Suite, ahora Azure Monitor

### <a name="release-to-market-1272016"></a>Lanzamiento al mercado (7/12/2016)

**Características:**

 **Creado para Skype Empresarial**

- Un solo toque para unirse a reuniones de Skype.
- Reunión de Skype experiencia optimizada para salas con vídeo HD de relleno de pantalla y audio de banda ancha HD
- Todos los participantes se pueden conectar a la reunión de Skype mediante el dispositivo que elijan desde el lugar en el que se encuentren.
- Invite a las personas desde su directorio, donde podrá consultar su disponibilidad en ese mismo momento o a través de una llamada de teléfono.
- Es compatible con los servicios de conferencias RTC y llamadas RTC de Skype Empresarial como sustitución del teléfono de conferencias independiente de su sala.

 **Transforme cualquier sala de reuniones**

- Una aplicación de reuniones de Skype dedicada y optimizada para el controlador táctil situado en el centro de la mesa y las pantallas frontales de gran tamaño.
- Reutilizar las inversiones existentes en la pantalla o proyectores de la sala
- Funciona en todo tipo de áreas de reuniones, desde los espacios más apiñados a las salas de conferencias más amplias.
- Los dispositivos de audio y vídeo certificados de Skype Empresarial están disponibles para diversos tamaños de salas.
- Ingestión cableada integrada para proyectar el uso compartido del escritorio en la sala y en la Reunión de Skype

 **Fácil de implementar, sencillo de administrar.**

- Dispositivo siempre encendido que activa automáticamente las pantallas cuando detecta personas en la sala
- Sencilla implementación y actualización de la aplicación de reuniones de Skype para UWP (Plataforma universal de Windows).
- Windows AppLocker bloquea el dispositivo con la aplicación de reuniones de Skype.
- Supervisada y administrada como dispositivo Windows 10 Enterprise a través de Intune y Configuration Manager (MDM)
- Fiabilidad de carácter empresarial.
- La formación que requieren los usuarios es muy poca puesto que ya conocen la interfaz de usuario de Skype.
- Se ejecuta en Surface Pro 4 tableta

<a name="See"> </a>
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar el entorno](rooms-prep.md)

[Compatibilidad con versiones de Salas de Microsoft Teams rama actual](rooms-lifecycle-support.md)

[Problemas conocidos](known-issues.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
