﻿---
title: "Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de MS (MSPL)"
TOCTitle: Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL)
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48276465
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013

 

_**Última modificación del tema:** 2014-09-26_

Una aplicación de servidor de lenguaje de procesamiento SIP (MSPL) es una aplicación de solo script que emplea un lenguaje de scripting en lugar de la Microsoft Lync 2010 API. MSPL reporta un mayor control sobre el filtrado y el comportamiento de los servidores proxy, así como una función para enviar mensajes específicos a aplicaciones SIP basadas en transacciones. MSPL se usa concretamente para filtrar y enrutar mensajes SIP. Las aplicaciones MSPL se ejecutan en el mismo proceso que el módulo UserServices, mientras que un programa basado en la Lync 2010 API se ejecuta en un proceso independiente.

Puede usar la página **Aplicación de servidor** en el grupo **Topología** del Panel de control de Lync Server para ver una lista de aplicaciones de servidor de MSPL que se ejecutan en los servidores front-end en su entorno de Lync Server 2013. La lista refleja los scripts que se encuentran disponibles para cada grupo, así como si están habilitados o son críticos. Los scripts se ejecutan en el orden en que aparecen.

Entre estos scripts se incluyen los siguientes:

  - ClientVersionFilter permite al administrador especificar la versión de los clientes compatibles con un grupo de servidores. El filtro de versiones del cliente comprueba la versión del cliente y puede impedir que el cliente inicie sesión o mostrar un mensaje que indique que está usando un cliente incompatible. El filtro de versiones del cliente también se puede configurar de modo que muestre un mensaje con la dirección URL de la última versión descargable del cliente.

  - TranslationService convierte un número marcado por el usuario en un número E.164, de acuerdo con las reglas de normalización definidas por el administrador. Para obtener información detallada, consulte [Reglas de traducción en Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation aplica la validación de federación a nivel de inquilino para los mensajes entre inquilinos y mensajes entrantes de las implementaciones externas.

  - UserServices es el componente de registro de SIP, presencia y conferencia de un servidor front-end. Proporciona características de mensajería instantánea, presencia y conferencia estrechamente integradas que se basan en el servidor proxy SIP.

  - InterClusterRouting es el responsable del enrutamiento de llamadas al grupo principal del registrador de los destinatarios de las llamadas. Para obtener información detallada, consulte [Componentes VoIP del servidor front-end para Lync Server 2013](lync-server-2013-front-end-server-voip-components.md)

  - IIMFilter (filtro inteligente de mensaje instantáneo) bloquea los mensajes que contienen direcciones URL en las que se puede hacer clic o que tratan de iniciar transferencias de archivos. IIMFilter también comprueba la versión del cliente en nombre del servidor. IIMFilter afecta a las transferencias de archivos que se inician con Lync Server o Communicator. De manera predeterminada, los vínculos en los que se puede hacer clic se deshabilitan agregando un carácter de subrayado antes del primer carácter del vínculo. Los administradores pueden cambiar este comportamiento para que el vínculo quede bloqueado. En ese caso, los mensajes que contengan direcciones URL en las que se puede hacer clic o que traten de iniciar una transferencia de archivos quedarán bloqueados por el servidor y no llegarán a los destinos previstos. IIMFilter se instala en todos los servidores que ejecutan Lync Server excepto los servidores proxy y los servidores de archivado.

  - UserPinService se usa para comprobar los números de identificación personal (PIN) para las conferencias de acceso telefónico local.

  - DefaultRouting es la aplicación de enrutamiento predeterminada para los servidores que ejecutan Lync Server. Está habilitada de forma predeterminada. La aplicación de enrutamiento está instalada en todos los servidores Standard Edition y Enterprise Edition.

  - ExumRouting enruta las llamadas a la mensajería unificada de Exchange Server. ExumRouting determina el servidor adecuado de mensajería unificada de Exchange al que se debe enrutar la llamada cuando se deposita un nuevo mensaje de correo de voz. También administra algunos otros aspectos de integración de la mensajería unificada, como el enrutamiento al operador automático y al acceso de suscriptor.

  - OutboundRouting determina la puerta de enlace que enruta una llamada a un número de teléfono de acuerdo con el número marcado y la autorización de marcado del usuario. OutboundRouting también administra el desvío de las llamadas si una puerta de enlace no puede procesarlas.

  - QoEAgent recibe informes de datos de calidad de la experiencia desde extremos a través de solicitudes SIP SERVICE y envía los datos a la cola de destino en el servidor de supervisión o a consumidores de terceros mediante HTTP POST. Para obtener información detallada, consulte [Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation aplica la validación de la federación a nivel de inquilino para los mensajes dirigidos a una implementación externa destinada.

  - AcpRouting envía solicitudes INVITE destinadas a la puerta de enlace entre un proveedor de conferencias de audio y un proveedor de conferencias de audio.

Los scripts que se ejecutan en servidores perimetrales incluyen lo siguiente:

  - IIMFilter

  - OptionsHandler responde **200 OK** a las solicitudes OPTIONS entrantes si la solicitud está destinada al servidor actual. Esta operación sirve para validar topologías.

## Vea también

#### Tareas

[Habilitar o deshabilitar una aplicación de servidor de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL)](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marcar una aplicación de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL) como crítica o no crítica](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)

