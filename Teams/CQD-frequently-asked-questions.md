---
title: Preguntas más frecuentes (P+F) del Panel de calidad de llamadas
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lea las preguntas más frecuentes (P+F) y las respuestas sobre Microsoft Teams panel de calidad de llamadas.
ms.openlocfilehash: f320bab549ee322c1254babd0feb49cc24419215
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823209"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F) del Panel de calidad de llamadas

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

[¿Por qué marca el CQD una llamada como "Buena" si uno o varios participantes de la reunión tuvieron una experiencia deficiente?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[¿Por qué veo una diferencia de hasta el 0,2 % en los valores de llamada y de recuento de usuarios en medidas y cómo obtener volúmenes más precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[¿Por qué no puedo ver EUII en el CQD?](#why-cant-i-see-euii-in-cqd)

[Estoy intentando usar el CQD para los informes de tipo de uso y me doy cuenta de que algunos de los datos están incompletos. ¿Por qué es eso?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[¿Por qué veo Skype Empresarial información en el CQD cuando solo he filtrado por Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas si sé que debería haber más entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[¿Por qué Wi-Fi conexiones VPN se muestran como cableadas en lugar de Wi-Fi?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[He activado la grabación basada en directivas en Teams y ahora las llamadas de punto a punto se marcan como conferencias. ¿Qué ha ocurrido?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>¿Por qué marca el CQD una llamada como "Buena" si uno o varios participantes de la reunión tuvieron una experiencia deficiente?

Consulte las reglas que usa el CQD para la [clasificación de transmisiones](stream-classification-in-call-quality-dashboard.md).
 
Para las transmisiones de audio, cualquiera de los cinco clasificadores (que se calculan para el promedio basado en la longitud de la llamada) podría estar dentro de parámetros "buenos". No significa que los usuarios no experimentaron algo que haya contribuido a una entrega de audio, estática o con problemas. 

Para determinar si se trataba de un problema de red, observe la diferencia entre los valores promedio de la sesión y los valores máximos. Los valores máximos son los máximos detectados y notificados durante la sesión.
 
Este es un ejemplo de cómo solucionar esta situación. Supongamos que toma un seguimiento de red durante una llamada y los primeros 20 minutos no hay paquetes perdidos, pero entonces tiene un intervalo de 1,5 segundos de paquetes y, después, es bueno para el resto de la llamada. El promedio va a ser <10% (0.1) Pérdida de paquetes incluso en un análisis RTP de seguimiento de Wireshark. ¿Cuál fue el máximo de pérdida de paquetes? 1,5 Segundos en un período de 5 segundos sería el 30 % (0,3). ¿Ocurrió durante el período de muestreo de 5 segundos (quizás o podría dividirse durante el período de muestreo)?
 
Si las métricas de red tienen un buen aspecto en los valores promedios y máximos, busque otros datos de telemetría: 
- Compruebe la Relación de eventos insuficiente de CPU para ver si los recursos de CPU disponibles detectados eran insuficientes y estaban generando mala calidad. 
- ¿Estaba el dispositivo de audio en modo Semidúplex para evitar comentarios debido a micrófonos que están demasiado cerca de los altavoces? 
- Compruebe la relación de eventos AEC AEC semidúplex del dispositivo. ¿Se producía un fallo en un dispositivo, como un micrófono, que introducía ruido o estática debido a las listas desplegables de audio USB cuando se conectaba a un concentrador o a una base de acoplamiento?  
- Comprueba las relaciones de eventos entre problemas de dispositivo y micrófono. ¿Funcionaba correctamente el propio dispositivo?  
- Comprueba las relaciones de eventos de captura y representación que no funcionan del dispositivo.


Para obtener más información sobre las dimensiones y medidas disponibles en telemetría del CQD, lea [Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

Para el ruido de fondo, compruebe la relación de evento de silencio para ver la duración del tiempo que los participantes se silenciaron.
 
Cree informes detallados en el CQD y filtre en el Id. de reunión para ver todos los usuarios y las transmisiones de una reunión y agregar los campos que le interesen. Es posible que un usuario que informe del problema no sea el que estaba experimentando el problema. Solo están informando de la experiencia.
 
La telemetría no llamará necesariamente al problema, pero puede ayudarte a comprender mejor dónde buscar e informar tus decisiones. ¿Se trata de actualizaciones de red, dispositivo, controlador o firmware, uso o usuario?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>¿Por qué veo una diferencia de hasta el 0,2 % en los valores de llamada y de recuento de usuarios en medidas y cómo obtener volúmenes más precisos? 

Para calcular el recuento de llamadas y las medidas de recuento de usuarios, se realiza una operación countif distinta con los identificadores de llamada o usuario del conjunto de datos. En conjuntos de datos grandes, hay un error de hasta el 0,2 % inherente a la operación countif distinta. Para obtener el volumen más preciso, debe confiar en las medidas de recuento de transmisiones, ya que no se basan en esta operación countif distinta. El filtrado para reducir el volumen de datos puede reducir el error, pero no puede eliminar este origen de error en distintos recuentos de llamadas y usuarios. Consulte [Dimensiones y medidas disponibles en el panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md) para las medidas que se ven afectadas.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>¿Por qué no puedo ver EUII en el CQD?

Estos roles de administrador pueden acceder al CQD, pero no pueden ver euii (información identificable para el usuario final):

- Lector de informes de Microsoft 365
- Especialista en soporte técnico de comunicaciones de Teams

Para obtener más información sobre los roles que pueden acceder al CQD, incluido EUII, lea [Asignar roles para acceder al CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Estoy intentando usar el CQD para los informes de tipo de uso y me doy cuenta de que algunos de los datos están incompletos. ¿Por qué es eso?

Las herramientas de administración de calidad de llamadas como CQD, Análisis de llamadas, Graph API CallRecord y Análisis en tiempo real se basan en telemetría de diagnóstico. La información que se muestra en Teams herramientas de administración de calidad de llamadas es tan completa como los datos de telemetría que recibimos de los clientes que participan en una llamada. Hay varios motivos por los que es posible que no recibamos telemetría completa, como interrupciones de red o [errores de configuración del firewall o proxy](/microsoft-365/enterprise/urls-and-ip-address-ranges). Seguimos trabajando para mejorar la confiabilidad y resistencia con la que Teams clientes ofrecen telemetría al servicio.

Teniendo esto en cuenta, no se admite el uso de herramientas de administración de calidad de llamadas para la generación de informes de uso. No están diseñadas para dar cabida ni están pensadas para estos tipos de escenarios de informes, y muchas estadísticas de uso no están disponibles y no estarán disponibles en estas herramientas. Teams Administración Centro ofrece una serie de [informes de uso](teams-analytics-and-reports/teams-reporting-reference.md) y un [informe de asistencia a](teams-analytics-and-reports/meeting-attendance-report.md) reuniones directamente desde el cliente de Teams.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>¿Por qué veo Skype Empresarial información en el CQD cuando solo he filtrado por Teams?

Al filtrar por Teams solo en informes del CQD (isTeams = 1), está filtrando para todas las llamadas en las que el *primer punto de conexión* está Teams. Si el *segundo punto de conexión* está Skype Empresarial, esa información se mostrará en el informe del CQD. Según los escenarios de los clientes, el CQD puede incluir llamadas de Skype Empresarial Server 2019 cuando se configura el [conector de datos de llamadas](/skypeforbusiness/hybrid/plan-call-data-connector). También puede incluir Skype llamadas bot (AA, CVI, VDI), eventos en directo y llamadas RTC.

Es posible quitar Skype Empresarial información de las consultas filtrando dimensiones como *Primera categoría de agente de usuario* y *Segunda categoría de agente de usuario*. También puede usar *el Par de categorías de agente de usuario* , que combina las dimensiones Primera y Segunda en un único filtro.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas si sé que debería haber más entradas?

El CQD está diseñado para consultas de datos resumidas y no está diseñado para la exportación de datos. Recomendamos reestructurar los informes, siempre que sea posible, para evitar que se supere el límite de 10.000 filas. Empiece consultando los KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, etc. Desde allí, puede explorar en profundidad las dimensiones cada vez más altas de cardinalidad. El departamento de soporte técnico y los informes de Location-Enhanced proporcionan buenos ejemplos de este flujo de trabajo de exploración en profundidad.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>¿Por qué Wi-Fi conexiones VPN se muestran como cableadas en lugar de Wi-Fi?

Este es el comportamiento que se espera. El proveedor de VPN ha creado un adaptador Ethernet virtual que se trata como una conexión cableada. Dado que no está correctamente etiquetado, el sistema operativo no sabe que es una conexión Wi-Fi y lo notifica como cableada.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>He activado la grabación basada en directivas en Teams y ahora las llamadas de punto a punto se marcan como conferencias. ¿Qué ha ocurrido?

Este es el comportamiento esperado cuando la grabación basada en directivas está habilitada en Microsoft Teams. Grabación basada en directivas usa un Teams Recorder Bot implementado en Microsoft Azure para capturar el contenido de las reuniones con fines de cumplimiento normativo. En la administración de calidad de llamadas, "punto a punto" es una descripción del flujo de tráfico multimedia, no de la interacción entre los usuarios. Dado que un Recorder Bot es en sí mismo una parte de la llamada, la llamada ya no es de punto a punto, sino de varias entidades. Las llamadas de varios participantes se clasifican como conferencias por Microsoft Teams, por lo que se indicarán como tales cuando vea estas llamadas en el CQD y otras herramientas de calidad de llamadas.

## <a name="related-articles"></a>Artículos relacionados

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload los datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
