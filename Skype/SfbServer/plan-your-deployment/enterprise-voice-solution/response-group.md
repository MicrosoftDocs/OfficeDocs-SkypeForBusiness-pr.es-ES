---
title: Planear la aplicación grupo de respuesta en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: La planeación de grupos de respuesta en Skype Empresarial Server Telefonía IP empresarial, lo que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos de archivos de audio.
ms.openlocfilehash: 5abf043531079e8eef707b8cdfc4efe70f8be4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813480"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planear la aplicación grupo de respuesta en Skype Empresarial Server

La planeación de grupos de respuesta en Skype Empresarial Server Telefonía IP empresarial, lo que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos de archivos de audio.

Si su organización tiene grupos de personas que responden y administran determinados tipos de llamadas, como atención al cliente, un servicio de asistencia interna o soporte telefónico general para un departamento, puede implementar la aplicación Grupo de respuesta para administrar este tipo de llamadas. La aplicación Grupo de respuesta enruta y pone en cola las llamadas entrantes a las personas designadas, que se conocen como agentes. Puede aumentar el uso de los servicios de asistencia telefónica y reducir los gastos de estos servicios por medio de estos grupos de respuesta.

Cuando el autor de la llamada llama a un grupo de respuesta, la llamada se enruta a un agente en función de un grupo de extensiones o de las respuestas que da el autor de la llamada a las preguntas de respuesta interactiva de voz (IVR). La aplicación Grupo de respuesta usa métodos de enrutamiento de grupos de respuesta estándar para enrutar la llamada al siguiente agente disponible. Entre los métodos de enrutamiento de llamadas admitidos se incluyen el enrutamiento en serie, el más largo inactivo, el paralelo, el round robin y el enrutamiento de operadores (es decir, se llama a todos los agentes al mismo tiempo para cada llamada entrante, independientemente de su presencia actual).

Si no hay ningún agente disponible, la llamada se mantiene en cola hasta que haya alguno. Mientras está en la cola, el autor de la llamada escucha música hasta que un agente disponible acepta la llamada. Si la cola está llena o si la llamada se encuentra fuera de servicio mientras está en la cola, es posible que el autor de la llamada oiga un mensaje y, a continuación, se desconecte o se transfiera a otro destino, como un número de teléfono o correo de voz diferente. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que deberán iniciar sesión en el grupo para poder aceptar las llamadas enrutadas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.

> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.

> [!NOTE]
> La aplicación Grupo de respuesta usa un servicio interno, denominado "Hacer coincidir", para poner en cola las llamadas y buscar agentes disponibles. Cada equipo que ejecuta la aplicación Grupo de respuesta ejecuta el servicio De coincidencia, pero solo hay un servicio de coincidencia por grupo activo a la vez; los demás son pasivos. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La aplicación grupo de respuesta hace todo lo posible para asegurarse de que el enrutamiento de llamadas y las colas continúen sin interrupciones. No obstante, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición se debe a que el servidor front-end está en desposición, también se perderán las llamadas que esté administrando actualmente el servicio de búsqueda de coincidencias activo en ese servidor front-end.

## <a name="response-group-workflows"></a>Flujos de trabajo de grupo de respuesta

Un flujo de trabajo define el comportamiento de una llamada desde el momento en que suena el teléfono hasta que alguien la atiende. El flujo de trabajo especifica la cola que se va a usar para poner la llamada en espera, así como el método de enrutamiento que se va a usar en grupos de extensiones o las preguntas y respuestas que se van a utilizar en grupos de respuesta interactivos. Un flujo de trabajo también define configuraciones como el mensaje de bienvenida, la música en espera, horario laboral y los días festivos.

> [!NOTE]
> Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos.

## <a name="management-of-response-groups"></a>Administración de grupos de respuesta

En Skype Empresarial Server, hay dos roles de administración disponibles para administrar grupos de respuesta: el administrador del grupo de respuesta y el administrador del grupo de respuesta. Los administradores del grupo de respuesta pueden administrar cualquier aspecto de cualquier grupo de respuesta. Los administradores de grupos de respuesta solo pueden administrar determinados aspectos y solo para los grupos de respuesta que poseen. El rol de administrador puede ayudarle a reducir los costos de administración, ya que puede delegar responsabilidades limitadas para grupos de respuesta específicos a cualquier usuario que esté habilitado para Telefonía IP empresarial. Ten en cuenta que un usuario puede ser administrador de grupo de respuesta y administrador de grupo de respuesta.

Para dar cabida al rol administrador, la aplicación Grupo de respuesta usa un tipo de flujo **de** trabajo administrado o no administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.

**Grupos de respuesta administrados y no administrados**

|**Tipo de grupo de respuesta**|**Descripción**|
|:-----|:-----|
|No administrado  <br/> | Los grupos de respuesta no administrados no tienen ningún director asignado. Solo el administrador del grupo de respuesta puede configurar estos grupos de respuesta. <br/>  Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola. <br/>  Al migrar grupos de respuesta de una versión anterior a Skype Empresarial Server, el tipo se establece en No administrado. <br/> |
|Administrados  <br/> | Los administradores de grupos de respuesta pueden configurar cualquier aspecto de los grupos de respuesta administrados. <br/>  Los administradores de grupos de respuesta no pueden ver ni modificar grupos de respuesta que no se les han asignado explícitamente. <br/>  Los administradores de grupos de respuesta solo pueden configurar algunas opciones para los grupos de respuesta que se les han asignado explícitamente. <br/>  Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados. <br/> |

En la tabla siguiente se describen las acciones que los administradores de grupos de respuesta pueden y no pueden realizar para los grupos de respuesta asignados.

**Capacidad del director de grupo de respuesta**

|**Puede configurar:**|**Puede crear, eliminar o configurar:**|**No se puede:**|
|:-----|:-----|:-----|
| Agents <br/>  Mensajes de bienvenida <br/>  Nombre del grupo de respuesta <br/>  Descripción <br/>  Número para mostrar <br/>  Horario comercial <br/>  Música en espera <br/>  Estado (activo/inactivo) <br/>  Flujos de trabajo de grupo de extensiones o flujos de trabajo de respuesta interactiva de voz (IVR) <br/> | Grupos de agentes <br/>  Colas <br/>  Conjuntos de vacaciones <br/> | Crear o eliminar ningún tipo de flujo de trabajo <br/>  Modificar la configuración principal de grupos de respuesta, como el **URI de SIP**, el **número de teléfono** o el **tipo de flujo de trabajo**.  <br/> |

Los administradores de grupos de respuesta pueden usar las siguientes herramientas para administrar los grupos de respuesta designados.

- Panel de control de Skype Empresarial Server

    > [!NOTE]
    > Los administradores de grupos de respuesta solo pueden administrar la configuración del grupo de respuesta con esta herramienta. Otras opciones de configuración de Skype Empresarial Server no están disponibles para los administradores.

- Herramienta de configuración de grupo de respuesta

- Shell de administración de Skype Empresarial Server

El grupo de respuesta se escala bien a entornos departamentales o de grupo de trabajo (para obtener más información, consulte Planeación de capacidad para grupo de [respuesta)](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)y se puede implementar en instalaciones telefónicas totalmente nuevas. Admite llamadas entrantes desde la Telefonía IP empresarial y desde la red del operador local. Los agentes pueden usar Skype Empresarial, Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition para realizar las llamadas que se les enrutan.

## <a name="deployment-and-requirements"></a>Implementación y requisitos

La aplicación Grupo de respuesta se habilita automáticamente al implementar Telefonía IP empresarial.

### <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

La aplicación grupo de respuesta tiene los mismos requisitos de hardware, requisitos de sistema operativo y requisitos previos de software que los servidores front-end.

Si usa archivos de Audio de Windows Media (.wma) para anuncios y música de Grupo de respuesta, todos los servidores front-end o servidores Standard Editions que ejecuten la aplicación Grupo de respuesta deben tener instalado El tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, El tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.

Grupo de respuesta usa **paquetes de idioma** para admitir el reconocimiento de texto a voz y voz. Estas tecnologías de voz se usan al configurar mensajes, como el mensaje de bienvenida y otros mensajes, y preguntas y respuestas interactivas de respuesta de voz (IVR). De forma predeterminada, los 26 paquetes de idioma admitidos se instalan al implementar Skype Empresarial Server.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación Grupo de respuesta usa los siguientes puertos:

- **Puerto 5071**   para solicitudes de escucha SIP

- **Puerto 8404 para**   comunicaciones entre servidores

    > [!NOTE]
    > Este puerto se usa para el servicio de coincidencia y es necesario cuando la aplicación Grupo de respuesta se implementa en un grupo de servidores que tiene más de un servidor front-end.

   > [!NOTE]
   > Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del Shell de administración de Skype Empresarial Server.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación Grupo de respuesta admite el formato de archivo wave (.wav) y el formato de archivo de audio de Windows Media (.wma) para mensajes de Grupo de respuesta, música en espera o preguntas de respuesta interactiva de voz (IVR).

El formato de archivo de audio de Windows Media requiere que el tiempo de ejecución de Windows Media Format esté instalado en servidores front-end que ejecuten Windows Server 2008 R2 y Windows Server 2008. Para más información, vea "Requisitos de software" anteriormente en esta sección.

#### <a name="supported-wave-file-formats"></a>Formatos de archivo wave compatibles

Todos los archivos wave deben cumplir los requisitos siguientes:

- Archivo de 8 bits o de 16 bits

- Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law

- Mono o estéreo

- 4 MB o menos

Para obtener el máximo rendimiento de los archivos wave, se recomienda usar un archivo wave mono de 16 bits a 16 kHz.

#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de archivo de audio Windows Media admitidos

Si usa un archivo de audio Windows Media, considere la posibilidad de usar velocidades de bits lentas y compruebe el rendimiento del sistema cuando se somete a carga.

Puede usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media. Para descargar Expression Encoder 4, vea [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) .

### <a name="response-group-configuration-tool-requirements"></a>Requisitos para la herramienta de configuración del grupo de respuesta

La Herramienta de configuración de grupo de respuesta admite las combinaciones de sistemas operativos y exploradores web que se describen en la tabla siguiente.

> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.

**Sistemas operativos y exploradores web compatibles**

|**Sistema operativo**|**Explorador web**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 con SP2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Consola del agente del grupo de respuesta

La consola de agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.

> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.

**Sistemas operativos y exploradores web compatibles**

|**Sistema operativo**|**Explorador web**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Compatibilidad con clientes

La aplicación Grupo de respuesta admite los siguientes clientes:

- Cliente de escritorio de Skype Empresarial

- Cliente de escritorio de Lync 2013

- Cliente de escritorio de Lync 2010

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> La aplicación grupo de respuesta no es compatible con los clientes móviles de Lync.

El cliente específico que puede usar depende del tipo de usuario del grupo de respuesta que sea:

- Los **autores de llamadas** pueden llamar a un grupo de respuesta mediante cualquiera de los clientes de la lista anterior y a través de un teléfono normal por la red telefónica conmutada (RTC).

- **Los agentes informales** (agentes que no inician y cerrar sesión en sus grupos para aceptar llamadas) pueden aceptar llamadas mediante Attendant, Lync o Lync Phone Edition. Los agentes informales inician sesión automáticamente en sus grupos cuando inician sesión en Skype Empresarial Server mediante uno de estos clientes.

- Los agentes **formales** (agentes que deben iniciar y cerrar sesión en sus grupos para aceptar llamadas) pueden aceptar llamadas usando Skype Empresarial y accediendo a la consola del agente desde el elemento de menú, o mediante el operador y el acceso a la consola del agente directamente desde Internet Explorer.

## <a name="capacity-planning"></a>Planeamiento de capacidad

En la tabla siguiente se describe el modelo de usuario de grupo de respuesta que puede usar como base para los requisitos de planeación de capacidad.

> [!NOTE]
> En los números de la tabla siguiente se supone que se usan archivos Wave (.wav) mono de 16 bits a 16 kHz para todos los archivos de audio del grupo de respuesta. Si usa otros formatos de archivo, como Windows Media Audio (.wma), los números pueden variar.

> [!IMPORTANT]
> Tenga en cuenta que para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder controlar las cargas de trabajo de todos los grupos de respuesta de ambos grupos.

**Modelo de usuario de grupo de respuesta**

|**Métrica**|**Por grupo de servidores Enterprise Edition  <br/> (con 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Llamadas entrantes por segundo  <br/> |16   <br/> |2   <br/> |
|Llamadas simultáneas conectadas a IVR o MoH  <br/> |480  <br/> |60  <br/> |
|Sesiones anónimas simultáneas (sin mensajería instantánea)  <br/> |224  <br/> |28  <br/> |
|Sesiones anónimas simultáneas (con mensajería instantánea)  <br/> |64  <br/> |8   <br/> |
|Agentes activos (formales e informales)  <br/> |2400  <br/> |2400  <br/> |
|Número de grupos de extensiones  <br/> |800  <br/> |800  <br/> |
|Número de grupos de IVR (usar el reconocimiento de voz)  <br/> |400  <br/> |400  <br/> |


