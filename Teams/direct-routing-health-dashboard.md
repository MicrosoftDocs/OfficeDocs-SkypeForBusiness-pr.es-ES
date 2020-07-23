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
description: Aprenda a usar el panel de estado para supervisar la conexión entre el controlador de borde de sesión y el enrutamiento directo.
ms.openlocfilehash: a75510340815489921a5dd67a204b6914a9539d4
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229116"
---
# <a name="health-dashboard-for-direct-routing"></a>Panel de estado para enrutamiento directo

El panel de estado para el enrutamiento directo le permite supervisar la conexión entre el controlador de borde de sesión (SBC) y la interfaz de enrutamiento directo.  Con el panel de estado, puede supervisar información sobre su SBC, el servicio de telefonía y los parámetros de red entre su SBC y la interfaz de enrutamiento directo. Esta información puede ayudarte a identificar los problemas, incluido el motivo de las llamadas interrumpidas. Por ejemplo, es posible que el SBC deje de enviar llamadas si un certificado de SBC ha expirado o si hay problemas de red. Consulte los [roles de administrador](using-admin-roles.md) para saber quién tiene acceso al panel de estado.

El panel de Estado supervisa dos niveles de información:

- Estado general del SBCs conectado
- Información detallada sobre el SBCs conectado

Puede ver el panel de estado en el centro de administración de Microsoft Teams y Skype empresarial.

## <a name="overall-health"></a>Estado general

El panel de estado proporciona la siguiente información relacionada con el estado general de la SBCs conectada:

 ![Muestra estadísticas del panel de estado](media/direct-routing-dashboard-stats1.png)

- **Resumen de enrutamiento directo** : se muestra el número total de SBCS registrado en el sistema. El registro significa que el administrador de inquilinos agregó un SBC mediante el comando New-CsOnlinePSTNGateway. Si se agregó la SBC en PowerShell pero nunca se conectó, el panel de estado lo muestra en un estado incorrecto.

- **SBC** : el FQDN del SBC emparejado.

- **Relación de efectividad de la red (NER)** : el ner mide la capacidad de una red de entregar llamadas midiendo el número de llamadas enviadas en comparación con el número de llamadas entregadas a un destinatario.  

   El NER mide la capacidad de las redes para enviar llamadas al terminal de la parte final, excluidas las acciones del usuario, como resultado de rechazos de llamadas.  Si el destinatario rechazó una llamada o envió la llamada al buzón de voz, la llamada se cuenta como una entrega correcta. Esto significa que un mensaje de respuesta, una señal de ocupado o un timbre sin respuesta se consideran llamadas correctas.
  
   Por ejemplo, supongamos que el enrutamiento directo envió una llamada al SBC y el SBC devuelve el código SIP "504 el tiempo de espera del servidor: el servidor intentó acceder a otro servidor al intentar procesar la solicitud y no recibió una respuesta de mensaje". Esta respuesta indica que hay un problema en el lado de SBC y esto disminuirá el NER en el panel de estado para este SBC.
  
   Debido a que la acción que realices puede depender del número de llamadas afectadas, el panel de estado muestra cuántas llamadas se han analizado para calcular un parámetro. Si el número de llamadas es menor que 100, el NER podría ser muy bajo, pero sigue siendo normal.

   La fórmula que se usa para calcular NER es la siguiente:

   NER = 100 x (llamadas respondidas + el usuario ocupado + timbre no responde + ataques de rechazo de terminal)/total

- **Duración media** de las llamadas: la información acerca de la duración media de las llamadas puede ayudarte a controlar la calidad de las llamadas. La duración media de una llamada RTC de 1:1 es de cuatro a cinco minutos.  Sin embargo, para cada empresa, este promedio puede diferir.  Microsoft recomienda establecer una línea base para la duración media de las llamadas de su empresa. Si este parámetro va muy por debajo de la línea base, puede indicar que los usuarios tienen problemas con la calidad de las llamadas o con la confiabilidad y están colgados antes de lo habitual. Si comienza a ver la duración media de las llamadas, por ejemplo, 15 segundos, es posible que las personas que llaman se cuelguen porque su servicio no funciona correctamente.

   Debido a que la acción que realices puede depender del número de llamadas afectadas, el panel de estado muestra cuántas llamadas se han analizado para calcular un parámetro.

- **Estado de conectividad de TLS** : conectividad TLS (seguridad de la capa de transporte) muestra el estado de las conexiones TLS entre el enrutamiento directo y la SBC. El panel de estado también analiza la fecha de expiración del certificado y advierte si un certificado se establece para que venza en un plazo de 30 días, de modo que los administradores pueden renovar el certificado antes de que se interrumpa el servicio.

   Al hacer clic en el mensaje de advertencia, puede ver una descripción detallada del problema en una ventana emergente a la derecha y recomendaciones sobre cómo corregir el problema.

- **Estado de las opciones del SIP** : de forma predeterminada, el SBC envía mensajes de opciones cada minuto. Esta configuración puede variar para diferentes proveedores de SBC. El enrutamiento directo advierte si las opciones de SIP no se envían o no están configuradas. Para obtener más información sobre la supervisión de las opciones del SIP y las condiciones cuando se puede marcar un SBC como no funcional, vea [supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md).

- **Estado de las opciones del SIP detallado** : además de mostrar que hay un problema con el flujo de opciones de SIP, el panel de estado también proporciona descripciones detalladas de los errores. Para acceder a la descripción, haz clic en el mensaje "WARNING" (ADVERTENCIA). Una ventana emergente a la derecha mostrará la descripción detallada del error.

   Los posibles valores de los mensajes de estado de las opciones de SIP son los siguientes:

    - Activo: el SBC está activo: el servicio de enrutamiento directo de Microsoft ve las opciones que fluyen en un intervalo normal.

    - ADVERTENCIA: sin opciones de SIP, el controlador de borde de sesión existe en la base de datos (el administrador lo creó mediante el comando New-CsOnlinePSTNGateway). Está configurado para enviar opciones de SIP, pero el servicio de enrutamiento directo nunca vio las opciones de SIP que devolvió este SBC.

    - ADVERTENCIA: los mensajes SIP no están configurados: la supervisión de Troncalización con las opciones de SIP no está activada. El sistema de llamadas de Microsoft usa las opciones SIP y la supervisión de protocolo de seguridad de la capa de transporte (TLS) para detectar el estado de los controladores de borde de la sesión conectada (SBCs) en el nivel de aplicación. Tendrá problemas si este tronco se puede alcanzar en el nivel de red (haciendo ping), pero el certificado ha expirado o la pila SIP no funciona. Microsoft recomienda habilitar el envío de las opciones del SIP para ayudarle a identificar esos problemas en un principio. Consulte la documentación de su fabricante de SBC para configurar el envío de opciones de SIP.

- **Capacidad de llamadas simultáneas** : puede especificar el límite de llamadas simultáneas que un SBC puede controlar mediante el comando New-or Set-CsOnlinePSTNGateway con el parámetro-MaxConcurrentSessions. Este parámetro calcula el número de llamadas que se han enviado o recibido mediante el enrutamiento directo con un SBC específico y la compara con el límite establecido. Nota: Si el SBC también controla las llamadas a diferentes sistemas PBX, este número no mostrará las llamadas simultáneas actuales.

## <a name="detailed-information-for-each-sbc"></a>Información detallada para cada SBC

También puede ver la información detallada para un SBC específico, tal como se muestra en la siguiente captura de pantalla:

![Detalles de SBC del panel de estado](media/direct-routing-dashboard-SBC-detail1.png)

La vista detallada muestra los siguientes parámetros adicionales:

- **Estado de conectividad de TLS** : es la misma métrica que la página "estado general".

- **Último estado de conectividad TLS** : muestra la hora en la que SBC hizo una conexión TLS con el servicio de enrutamiento directo;

- **Estado de las opciones del SIP** : la misma métrica que en la página "estado general".

- **Opciones del SIP última marca** : hora en la que se recibieron las opciones SIP la última vez.

- **Estado de SBC** : estado general de SBC, basado en todos los parámetros supervisados.

- **Llamada simultánea**: muestra el número de llamadas simultáneas que controla el SBC. Esta información es útil para predecir la cantidad de canales simultáneos que necesita y ver la tendencia. Puede deslizar los datos por número de días y dirección de llamada (entrante o saliente/todas las transmisiones).

- **Parámetros de red** : todos los parámetros de red se miden desde la interfaz de enrutamiento directo hasta el controlador de borde de la sesión. Para obtener más información sobre los valores recomendados, consulte [preparar la red de su organización para Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)y mire los valores recomendados de borde del cliente a Microsoft Edge.

   - Vibración: es la medición de milisegundos de variación en el tiempo de retraso de propagación de red calculado entre dos puntos de conexión con RTCP (el protocolo de control RTP).

   - Pérdida de paquetes: es una medida de paquete que no pudo llegar. se calcula entre dos puntos finales.

   - Latencia: (también conocido como tiempo de ida y vuelta) es la cantidad de tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse el reconocimiento de esa señal. Este tiempo de retardo consiste en los tiempos de propagación entre los dos puntos de una señal.

   Puede deslizar los datos por número de días y dirección de llamada (entrante o saliente/todas las transmisiones).

**Relación de eficacia de red** : este es el mismo parámetro que aparece en el panel de estado general, pero con la opción de segmentar los datos por serie de tiempo o dirección de llamada.
