---
title: Panel de estado para enrutamiento directo
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo usar el panel de estado para supervisar la conexión entre el controlador de borde de sesión y el enrutamiento directo.
ms.openlocfilehash: a75510340815489921a5dd67a204b6914a9539d4
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229116"
---
# <a name="health-dashboard-for-direct-routing"></a>Panel de estado para enrutamiento directo

El panel de estado de enrutamiento directo le permite supervisar la conexión entre el controlador de borde de sesión (SBC) y la interfaz de enrutamiento directo.  Con el panel de estado, puede supervisar la información sobre su SBC, el servicio de telefonía y los parámetros de red entre su SBC y la interfaz de enrutamiento directo. Esta información puede ayudarle a identificar problemas, incluido el motivo por el que se descartan llamadas. Por ejemplo, la SBC puede dejar de enviar llamadas si un certificado del SBC ha expirado o si hay problemas de red. Consulte los [roles de administrador](using-admin-roles.md) para saber quién tiene acceso al panel de estado.

El panel de estado supervisa dos niveles de información:

- Estado general de los SBC conectados
- Información detallada sobre los SBC conectados

Puede ver el panel de estado en Microsoft Teams y el Centro de administración de Skype Empresarial.

## <a name="overall-health"></a>Estado general

El Panel de estado proporciona la siguiente información relacionada con el estado general de los SBC conectados:

 ![Muestra estadísticas del panel de estado](media/direct-routing-dashboard-stats1.png)

- **Resumen de enrutamiento directo:** muestra el número total de BDC registrados en el sistema. El registro significa que el administrador de inquilinos agregó un SBC mediante el New-CsOnlinePSTNGateway inquilino. Si el SBC se agregó en PowerShell, pero nunca se conectó, el panel de estado lo muestra con un estado incorrecto.

- **SBC:** el FQDN de la SBC emparejada.

- **Network Effectiveness Ratio (NER):** el NER mide la capacidad de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas que se reciben a un destinatario.  

   El NER mide la capacidad de las redes para entregar llamadas al terminal de extremo extremo, excepto las acciones realizadas por el usuario que produce rechazos en las llamadas.  Si el destinatario rechazó una llamada o envió la llamada al correo de voz, la llamada se contabiliza como una entrega correcta. Esto significa que un mensaje de respuesta, una señal de ocupado o un tono sin respuesta se consideran llamadas correctas.
  
   Por ejemplo, suponga que el enrutamiento directo envió una llamada a la SBC y la SBC devuelve el código SIP "Tiempo de espera del servidor 504: el servidor intentó obtener acceso a otro servidor al intentar procesar la solicitud y no recibió una respuesta inmediata". Esta respuesta indica que hay un problema en el lado de SBC y esto reducirá el NER en el panel de estado para este SBC.
  
   Dado que la acción que se debe realizar puede depender del número de llamadas afectadas, el panel de estado muestra cuántas llamadas se analizaron para calcular un parámetro. Si el número de llamadas es menor que 100, el NER podría ser bastante bajo, pero seguir siendo normal.

   La fórmula usada para calcular NER es la siguiente:

   NER = 100 x (llamadas contestadas + Ocupado por el usuario + Anillo sin respuesta + Rechaces de terminal)/Total de llamadas

- **Duración media de la** llamada: la información sobre la duración media de la llamada puede ayudarle a supervisar la calidad de las llamadas. La duración media de una llamada RTC de 1:1 es de cuatro a cinco minutos.  Sin embargo, para cada empresa, este promedio puede diferir.  Microsoft recomienda establecer una línea base para la duración de llamada media de su empresa. Si este parámetro baja significativamente de la línea base, puede indicar que los usuarios están teniendo problemas con la calidad o la confiabilidad de las llamadas y que se cuelgan antes de lo habitual. Si empieza a ver una duración de llamada media extremadamente baja, por ejemplo, 15 segundos, es posible que las llamadas se cedamos porque el servicio no funciona correctamente.

   Dado que la acción que se debe realizar puede depender del número de llamadas afectadas, el panel de estado muestra cuántas llamadas se analizaron para calcular un parámetro.

- **Estado de conectividad TLS:** la conectividad TLS (Seguridad de la capa de transporte) muestra el estado de las conexiones TLS entre enrutamiento directo y SBC. El panel de estado también analiza la fecha de expiración del certificado y avisa si se establece que el certificado expire en un plazo de 30 días para que los administradores puedan renovar el certificado antes de que se interrumpa el servicio.

   Al hacer clic en el mensaje de advertencia, puede ver una descripción detallada del problema en una ventana emergente a la derecha y recomendaciones sobre cómo corregir el problema.

- **Estado de las opciones SIP:** de forma predeterminada, la SBC envía mensajes de opciones cada minuto. Esta configuración puede variar para distintos proveedores de SBC. El enrutamiento directo avisa si las opciones SIP no se envían o no están configuradas. Para obtener más información sobre la supervisión de opciones SIP y las condiciones en las que un SBC puede marcarse como no funcional, consulte Supervisar y solucionar problemas [de enrutamiento directo.](direct-routing-monitor-and-troubleshoot.md)

- **Estado detallado de las** opciones SIP: además de mostrar que hay un problema con el flujo de opciones SIP, el panel de estado también proporciona descripciones detalladas de los errores. Puede acceder a la descripción haciendo clic en el mensaje "Advertencia". Una ventana emergente a la derecha mostrará la descripción detallada del error.

   Los posibles valores de los mensajes de estado de las opciones SIP son los siguientes:

    - Activo: el SBC está activo: el servicio de enrutamiento directo de Microsoft ve las opciones que fluyen en un intervalo regular.

    - Advertencia, ninguna opción SIP: el controlador de borde de sesión existe en la base de datos (el administrador lo creó con el comando New-CsOnlinePSTNGateway). Está configurado para enviar opciones de SIP, pero el servicio de enrutamiento directo nunca vio las opciones SIP que regresan de este SBC.

    - Advertencia, los mensajes SIP no están configurados: la supervisión de troncos con opciones SIP no está activada. Microsoft Calling System usa opciones SIP y supervisión de enlace de seguridad de la capa de transporte (TLS) para detectar el estado de los controladores de borde de sesión (SBCs) conectados en el nivel de la aplicación. Tendrá problemas si se puede llegar a este tronco en el nivel de red (mediante ping), pero el certificado ha expirado o la pila SIP no funciona. Para ayudar a identificar antes estos problemas, Microsoft recomienda habilitar el envío de opciones de SIP. Compruebe la documentación del fabricante de SBC para configurar las opciones de envío de SIP.

- **Capacidad de llamadas** simultáneas: puede especificar el límite de llamadas simultáneas que puede controlar un SBC mediante el comando Nuevo o Set-CsOnlinePSTNGateway con el parámetro -MaxConcurrentSessions. Este parámetro calcula cuántas llamadas se han enviado o recibido por enrutamiento directo mediante un SBC específico y lo compara con el límite establecido. Nota: Si la SBC también controla las llamadas a diferentes PBX, este número no mostrará las llamadas simultáneas reales.

## <a name="detailed-information-for-each-sbc"></a>Información detallada para cada SBC

También puede ver la información detallada de un SBC específico, como se muestra en la siguiente captura de pantalla:

![Detalles de SBC del panel de estado](media/direct-routing-dashboard-SBC-detail1.png)

La vista detallada muestra los siguientes parámetros adicionales:

- **Estado de conectividad TLS:** es la misma métrica que se muestra en la página "Estado general";

- **Último estado de conectividad TLS:** muestra la hora en que la SBC realizó una conexión TLS al servicio de enrutamiento directo;

- **Estado de las opciones SIP:** la misma métrica que se muestra en la página "Mantenimiento general".

- **Última vez que se comprobaron** las opciones SIP: hora en la que las opciones SIP se recibieron por última vez.

- **Estado SBC:** estado general de la SBC, basado en todos los parámetros supervisados.

- **Llamada simultánea:** muestra cuántas llamadas simultáneas controló la SBC. Esta información es útil para predecir el número de canales simultáneos que necesita y ver la tendencia. Puede deslizar los datos por número de días y la dirección de la llamada (transmisiones entrantes,salientes/todas).

- **Parámetros de red:** todos los parámetros de red se miden desde la interfaz de enrutamiento directo al controlador de borde de sesión. Para obtener información sobre los valores recomendados, consulte Preparar la red de su organización para [Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)y mire los valores recomendados del perímetro del cliente hasta Microsoft Edge.

   - Vibración: es la medida en milisegundos de la variación en el tiempo de retraso en la propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).

   - Pérdida de paquetes: es una medición de paquetes que no se pudieron llegar; se calcula entre dos puntos de conexión.

   - Latencia: (también conocido como tiempo de ida y vuelta) es el tiempo que tarda una señal en enviarse más el tiempo que tarda en recibirse la confirmación de dicha señal. Este retraso en el tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.

   Puede deslizar los datos por número de días y la dirección de la llamada (transmisiones entrantes,salientes/todas).

**Relación de eficacia de red:** este es el mismo parámetro que aparece en el panel Estado general, pero con la opción de segmentar los datos por serie temporal o por dirección de llamada.
