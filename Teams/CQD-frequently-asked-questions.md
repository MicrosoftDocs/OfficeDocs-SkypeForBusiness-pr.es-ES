---
title: Preguntas más frecuentes (PREGUNTAS FRECUENTES) del Panel de calidad de llamadas (CQD)
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
description: Lea las preguntas más frecuentes (PREGUNTAS FRECUENTES) y las respuestas Microsoft Teams panel de calidad de llamadas (CQD).
ms.openlocfilehash: 81c6478147e0959ca97b67ee0f01632478c0eb38
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401904"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Preguntas más frecuentes (PREGUNTAS FRECUENTES) del Panel de calidad de llamadas (CQD)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

[¿Por qué CQD marca una llamada como "Buena" si uno o varios participantes de la reunión tuvieron una mala experiencia?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[¿Por qué veo hasta un 0,2 % de diferencia en los valores de llamadas y recuento de usuarios en las medidas y cómo obtener volúmenes más precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[¿Por qué no puedo ver EUII en CQD?](#why-cant-i-see-euii-in-cqd)

[Estoy intentando usar CQD para informes de tipo de uso y encuentro que algunos de los datos están incompletos, ¿por qué es eso?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[¿Por qué veo Skype Empresarial en CQD cuando he filtrado para Teams solo?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas cuando sé que debería haber más entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[¿Por qué Wi-Fi conexiones VPN se muestran como cableadas en lugar de wi-fi?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[He activado la grabación basada en directivas en Teams y ahora las llamadas punto a punto se marcan como Conferencias, ¿qué ha ocurrido?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>¿Por qué CQD marca una llamada como "Buena" si uno o varios participantes de la reunión tuvieron una mala experiencia?

Consulte las reglas que CQD usa para la [clasificación de transmisiones.](stream-classification-in-call-quality-dashboard.md)
 
Para las transmisiones de audio, cualquiera de los cinco clasificadores, que se calculan para el promedio según la longitud de la llamada, podría estar dentro de los parámetros "buenos". Esto no significa que los usuarios no experimentaron algo que contribuyese a una deserción de audio, estática o problemas. 

Para determinar si se trataba de un problema de red, mire el delta entre los valores medios de la sesión y los valores máximos. Los valores máximos son el máximo detectado e notificado durante la sesión.
 
Este es un ejemplo de cómo solucionar esta situación. Supongamos que hace un seguimiento de red durante una llamada y los primeros 20 minutos no hay paquetes perdidos, pero después tiene un espacio de 1,5 segundos de paquetes y, a continuación, es bueno para el resto de la llamada. El promedio se va a <10 % (0,1) pérdida de paquetes incluso en un análisis de RTP de seguimiento de Wireshark. ¿Cuál era la pérdida máxima de paquetes? 1,5 segundos en un período de 5 segundos sería el 30 % (0,3). ¿Esto ocurrió dentro del período de muestreo de 5 segundos (quizás o podría dividirse en el período de muestreo)?
 
Si las métricas de red tienen un buen aspecto en los promedios y los valores máximos, busque otros datos de telemetría: 
- Compruebe la relación de eventos insuficiente de la CPU para ver si los recursos de CPU detectados disponibles eran insuficientes y causaban mala calidad. 
- ¿Estaba el dispositivo de audio en modo semidúplex para evitar comentarios debido a micrófonos que están demasiado cerca de los altavoces? 
- Compruebe la relación de eventos AEC a doble cara del dispositivo. ¿El dispositivo presentaba problemas de error o el micrófono presentaba problemas al introducir ruido o estático debido a las salidas de audio USB cuando se conectaba a un hub o base de acoplamiento?  
- Compruebe las relaciones de eventos Problemas del dispositivo y Micrófono. ¿Funcionaba el propio dispositivo correctamente?  
- Compruebe las relaciones de eventos de captura y representación del dispositivo que no funcionan.


Para obtener más información sobre las dimensiones y medidas disponibles en telemetría CQD, lea Dimensiones y [medidas disponibles en Panel](dimensions-and-measures-available-in-call-quality-dashboard.md)de calidad de llamadas.

Para el ruido de fondo, compruebe la relación del evento de silenciamiento para ver la duración del tiempo que los participantes se silenciaron.
 
Cree informes detallados en CQD y filtre en Id. de reunión para ver todos los usuarios y transmisiones de una reunión y agregar los campos que le interesan. Es posible que un usuario que informe del problema no sea el que estaba teniendo el problema. Solo están informando de la experiencia.
 
La telemetría no necesariamente resolverá el problema, pero puede ayudarle a comprender mejor dónde buscar e informar a sus decisiones. ¿Es la red, el dispositivo, el controlador o las actualizaciones de firmware, el uso o el usuario?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>¿Por qué veo hasta un 0,2 % de diferencia en los valores de llamadas y recuento de usuarios en las medidas y cómo obtener volúmenes más precisos? 

Para calcular las medidas de recuento de llamadas y recuento de usuarios, se realiza una operación countif distinta con los identificadores de llamada o de usuario del conjunto de datos. En conjuntos de datos grandes, hay un error de hasta un 0,2 % inherente a la operación countif distinta. Para obtener el volumen más preciso, debe basarse en las medidas de recuento de transmisiones, ya que no se basan en esta operación countif distinta. Filtrar para reducir el volumen de datos puede reducir el error, pero no puede eliminar esta fuente de error en diferentes recuentos de llamadas y usuarios. Consulte [Dimensiones y medidas disponibles en el Panel de calidad](dimensions-and-measures-available-in-call-quality-dashboard.md) de llamadas para qué medidas se ven afectadas.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>¿Por qué no puedo ver EUII en CQD?

Estos roles de administrador pueden obtener acceso a CQD, pero no pueden ver EUII (información de identificación del usuario final):

- Microsoft 365 de informes
- Teams de soporte técnico de comunicaciones

Para obtener más información sobre los roles que pueden tener acceso a CQD ,incluido EUII, lea Asignar roles para obtener acceso [a CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Estoy intentando usar CQD para informes de tipo de uso y encuentro que algunos de los datos están incompletos, ¿por qué es eso?

Las herramientas de administración de calidad de llamadas como CQD, Call Analytics, CallRecord Graph API y Análisis en tiempo real se basan en telemetría de diagnóstico. La información que mostramos en Teams de administración de calidad de llamadas es tan completa como los datos de telemetría que recibimos de los clientes que participan en una llamada. Hay varias razones por las que es posible que no recibamos telemetría completa, como interrupciones de red, [o configuraciones incorrectas](/microsoft-365/enterprise/urls-and-ip-address-ranges.md)de firewall o proxy. Seguimos trabajando para mejorar la confiabilidad y resistencia con la que Teams clientes entregan telemetría al servicio.

Con esto en mente, recomendamos no depender de las herramientas de administración de calidad de llamadas para informes de uso. Teams centro de administración ofrece una serie de informes de uso [y](teams-analytics-and-reports/teams-reporting-reference.md)un informe de asistencia [a](teams-analytics-and-reports/meeting-attendance-report.md) reuniones está disponible directamente desde Teams cliente.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>¿Por qué veo Skype Empresarial en CQD cuando he filtrado para Teams solo?

Al filtrar por Teams solo en informes CQD (isTeams = 1), está  filtrando para todas las llamadas en las que se encuentra el primer punto de conexión Teams. Si el *segundo punto de* conexión Skype Empresarial, esa información se mostrará en el informe CQD. Según los escenarios de los clientes, CQD puede incluir Skype Empresarial Server llamadas de 2019 cuando [el](/skypeforbusiness/hybrid/plan-call-data-connector.md) conector de datos de llamada está configurado. También puede incluir llamadas Skype Bot (AA, CVI, VDI), Live Events y llamadas RTC.

Es posible quitar información Skype Empresarial de las consultas filtrando en dimensiones  como Primera categoría de agente de usuario y Segunda categoría *de agente de usuario.* También puede usar el par *de categorías agente de usuario* que combina las dimensiones Primera y Segunda en un único filtro.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas cuando sé que debería haber más entradas?

CQD está diseñado para consultas de datos resumidos y no está diseñado para la exportación de datos. Recomendamos que se restructuran los informes, siempre que sea posible, para evitar que se supere el límite de 10 000 filas. Empiece por ver sus KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, entre otras. Desde allí, puede explorar en profundidad las dimensiones de mayor cardinalidad. Tanto el Departamento de soporte técnico como Location-Enhanced informes proporcionan buenos ejemplos de este flujo de trabajo de exploración en profundidad.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>¿Por qué Wi-Fi conexiones VPN se muestran como cableadas en lugar de wi-fi?

Este es el comportamiento que se espera. El proveedor de VPN creó un adaptador ethernet virtual que se trata como una conexión por cable. Puesto que no está etiquetado correctamente, el sistema operativo no sabe que es una conexión Wi-Fi y la notifica como cableada.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>He activado la grabación basada en directivas en Teams y ahora las llamadas punto a punto se marcan como Conferencias, ¿qué ha ocurrido?

Este es el comportamiento esperado cuando la grabación basada en directivas está habilitada en Microsoft Teams. Grabación basada en directivas usa un bot Teams recorder implementado en Microsoft Azure para capturar el contenido de la reunión con fines de cumplimiento. En la administración de calidad de llamadas, "punto a punto" es una descripción del flujo de tráfico multimedia, no de la interacción entre los usuarios. Dado que un bot de grabadora es en sí mismo una parte de la llamada, la llamada ya no es punto a punto, sino una llamada de varias partes. Las llamadas de varias partes se clasifican como conferencias por Microsoft Teams, por lo que se indicarán como tales cuando vea estas llamadas en CQD y otras herramientas de calidad de llamadas.

## <a name="related-articles"></a>Artículos relacionados

[Mejorar y supervisar la calidad de las llamadas Teams](monitor-call-quality-qos.md)

[¿Qué es CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload inquilino y datos de creación](CQD-upload-tenant-building-data.md)

[Datos e informes de CQD](CQD-data-and-reports.md)

[Usar CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencias en CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
