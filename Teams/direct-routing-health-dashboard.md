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
description: Obtenga información sobre cómo usar el Panel de estado para supervisar la conexión entre el controlador de borde de sesión y el enrutamiento directo.
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122234"
---
# <a name="health-dashboard-for-direct-routing"></a>Panel de estado para enrutamiento directo

El panel de estado para enrutamiento directo le permite supervisar la conexión entre el controlador de borde de sesión (SBC) y la interfaz de enrutamiento directo.  Con el Panel de estado, puede supervisar la información sobre su SBC, el servicio de telefonía y los parámetros de red entre su SBC y la interfaz de enrutamiento directo. Esta información puede ayudarle a identificar problemas, incluido el motivo de las llamadas que se han eliminado. Por ejemplo, es posible que el SBC deje de enviar llamadas si un certificado del SBC ha expirado o si hay problemas de red. Vea los [roles de administrador](using-admin-roles.md) para saber quién tiene acceso al panel de estado.

Panel de estado supervisa dos niveles de información:

- Estado general de los SBC conectados
- Información detallada sobre los SBC conectados

Puede ver el Panel de estado en Microsoft Teams y en el Centro de administración de Skype Empresarial.

## <a name="overall-health"></a>Estado general

El panel de estado proporciona la siguiente información relacionada con el estado general de los SBC conectados:

 ![Muestra estadísticas del panel de estado](media/direct-routing-dashboard-stats1.png)

- **Resumen de enrutamiento directo:** muestra el número total de SBC registrados en el sistema. Registro significa que el administrador de inquilinos agregó un SBC mediante el New-CsOnlinePSTNGateway usuario. Si el SBC se agregó en PowerShell, pero nunca se conectó, el Panel de estado lo muestra en un estado incorrecto.

- **SBC:** el FQDN del SBC emparejado.

- **Relación de eficacia de red (NER):** el NER mide la capacidad de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas entregadas a un destinatario.  

   El NER mide la capacidad de las redes para entregar llamadas al terminal de extremo lejano, excluyendo las acciones de usuario que se traducen en rechazos de llamadas.  Si el destinatario rechazó una llamada o envió la llamada al correo de voz, la llamada se cuenta como una entrega correcta. Esto significa que un mensaje de respuesta, una señal ocupada o un anillo sin respuesta se consideran llamadas correctas.
  
   Por ejemplo, supongamos que Enrutamiento directo ha enviado una llamada al SBC y el SBC devuelve el código SIP "504 Server Time-out: el servidor intentó obtener acceso a otro servidor al intentar procesar la solicitud y no recibió una respuesta rápida". Esta respuesta indica que hay un problema en el lado de SBC y esto disminuirá el NER en el panel de estado de este SBC.
  
   Dado que la acción que tome puede depender del número de llamadas afectadas, el Panel de estado muestra cuántas llamadas se analizaron para calcular un parámetro. Si el número de llamadas es menor que 100, el NER puede ser bastante bajo, pero seguir siendo normal.

   La fórmula usada para calcular NER es:

   NER = 100 x (Llamadas respondidas + Usuario ocupado + Llamar sin respuesta + Rechazar ataques terminales)/Total de llamadas

- **Duración media de la** llamada: la información sobre la duración media de la llamada puede ayudarle a supervisar la calidad de las llamadas. La duración media de una llamada RTC de 1:1 es de cuatro a cinco minutos.  Sin embargo, para cada empresa, este promedio puede diferir.  Microsoft recomienda establecer una línea base para la duración media de la llamada de su empresa. Si este parámetro va significativamente por debajo de la línea base, puede indicar que los usuarios tienen problemas con la calidad o la confiabilidad de las llamadas y que se cuelgan antes de lo habitual. Si empieza a ver una duración media de llamada extremadamente baja, por ejemplo 15 segundos, es posible que los autores de llamadas se resalten porque el servicio no funciona correctamente.

   Dado que la acción que tome puede depender del número de llamadas afectadas, el Panel de estado muestra cuántas llamadas se analizaron para calcular un parámetro.

- **Estado de conectividad tls:** la conectividad TLS (Seguridad de capa de transporte) muestra el estado de las conexiones TLS entre enrutamiento directo y SBC. El panel de estado también analiza la fecha de expiración del certificado y advierte si un certificado está configurado para expirar en un plazo de 30 días para que los administradores puedan renovar el certificado antes de que se interrumpa el servicio.

   Al hacer clic en el mensaje de advertencia, puede ver una descripción detallada del problema en una ventana emergente de la derecha y recomendaciones sobre cómo solucionar el problema.

- **Estado de las opciones SIP:** de forma predeterminada, el SBC envía mensajes de opciones cada minuto. Esta configuración puede variar para distintos proveedores de SBC. Enrutamiento directo advierte si las opciones SIP no se envían o no están configuradas. Para obtener más información sobre la supervisión de opciones SIP y las condiciones en las que un SBC se puede marcar como no funcional, vea Supervisar y solucionar problemas [de enrutamiento directo.](direct-routing-monitor-and-troubleshoot.md)

- **Estado de las opciones SIP** detalladas: además de mostrar que hay un problema con el flujo de opciones SIP, el panel de estado también proporciona descripciones detalladas de los errores. Puede acceder a la descripción haciendo clic en el mensaje "Advertencia". Una ventana emergente de la derecha mostrará la descripción detallada del error.

   Los posibles valores de los mensajes de estado de las opciones SIP son los siguientes:

    - Activo: el SBC está activo: el servicio de enrutamiento directo de Microsoft ve las opciones fluyendo en un intervalo regular.

    - Advertencia, sin opciones SIP: el controlador de borde de sesión existe en la base de datos (el administrador lo creó con el comando New-CsOnlinePSTNGateway). Está configurado para enviar opciones SIP, pero el servicio de enrutamiento directo nunca vio las opciones SIP que regresan de este SBC.

    - Advertencia, los mensajes SIP no están configurados: la supervisión de troncos con opciones SIP no está activada. Microsoft Calling System usa las opciones SIP y la supervisión de protocolo de enlace de seguridad de la capa de transporte (TLS) para detectar el estado de los controladores de borde de sesión (SBC) conectados en el nivel de la aplicación. Tendrá problemas si este tronco se puede alcanzar en el nivel de red (mediante ping), pero el certificado ha expirado o la pila SIP no funciona. Para ayudar a identificar estos problemas antes, Microsoft recomienda habilitar el envío de opciones sip. Compruebe la documentación del fabricante de SBC para configurar las opciones de envío de SIP.

- **Capacidad de llamadas simultáneas:** puede especificar el límite de llamadas simultáneas que puede controlar un SBC mediante el comando Nuevo o Set-CsOnlinePSTNGateway con el parámetro -MaxConcurrentSessions. Este parámetro calcula cuántas llamadas se enviaron o recibieron mediante enrutamiento directo con un SBC específico y lo compara con el límite establecido. Nota: Si el SBC también controla las llamadas a distintos PBX, este número no mostrará las llamadas simultáneas reales.

## <a name="detailed-information-for-each-sbc"></a>Información detallada para cada SBC

También puede ver la información detallada de un SBC específico como se muestra en la siguiente captura de pantalla:

![Detalles del SBC del panel de estado](media/direct-routing-dashboard-SBC-detail1.png)

La vista detallada muestra los siguientes parámetros adicionales:

- **Estado de conectividad TLS:** esta es la misma métrica que en la página "Estado general";

- **Último estado de conectividad TLS:** muestra la hora en que el SBC realizó una conexión TLS al servicio de enrutamiento directo;

- **Estado de las opciones SIP:** la misma métrica que en la página "Estado general".

- **Las opciones SIP se marcaron por** última vez: hora en la que se recibieron las opciones SIP la última vez.

- **Estado de SBC:** estado general del SBC, en función de todos los parámetros supervisados.

- **Llamada simultánea:** muestra cuántas llamadas simultáneas ha manipulado el SBC. Esta información es útil para predecir el número de canales simultáneos que necesita y ver la tendencia. Puede deslizar los datos por número de días y dirección de llamada (entrante/saliente/Todas las transmisiones).

- **Parámetros de red:** todos los parámetros de red se miden desde la interfaz de enrutamiento directo hasta el controlador de borde de sesión. Para obtener información sobre los valores recomendados, vea Preparar la red de su organización para [Microsoft Teams](./prepare-network.md)y consulte los valores recomendados de Cliente perimetral a Microsoft Edge.

   - Vibración: es la medida de milisegundos de variación en el tiempo de retraso de propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).

   - Pérdida de paquetes: es una medida de paquete que no ha podido llegar; se calcula entre dos puntos de conexión.

   - Latencia: (también conocido como tiempo de ida y vuelta) es el tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse la confirmación de esa señal. Este retraso de tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.

   Puede deslizar los datos por número de días y dirección de llamada (entrante/saliente/Todas las transmisiones).

**Relación de eficacia de** red: este es el mismo parámetro que aparece en el panel Estado general, pero con la opción de segmentar los datos por serie temporal o dirección de llamada.