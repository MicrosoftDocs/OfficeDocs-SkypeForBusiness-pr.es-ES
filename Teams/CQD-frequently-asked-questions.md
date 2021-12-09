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
ms.openlocfilehash: 4d0d0bbbc35ac130755e61075408e9de80f1c09c
ms.sourcegitcommit: d976e49943aedd511bd6a80b02afeac4a6453406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61362547"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Preguntas más frecuentes (PREGUNTAS FRECUENTES) del Panel de calidad de llamadas (CQD)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

[¿Por qué CQD marca una llamada como "Buena" si uno o varios participantes de la reunión tuvieron una mala experiencia?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[¿Por qué veo hasta un 0,2 % de diferencia en los valores de llamadas y recuento de usuarios en las medidas y cómo obtener volúmenes más precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[¿Por qué no puedo ver EUII en CQD?](#why-cant-i-see-euii-in-cqd)

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
- ¿Estaba el dispositivo de audio en modo Semidúplex para evitar comentarios debido a los micrófonos que se cierran a los altavoces? 
- Compruebe la relación de eventos AEC a doble cara del dispositivo. ¿El dispositivo presentaba problemas de error o el micrófono presentaba problemas de ruido o estático debido a las salidas de audio USB cuando se conectaba a un hub o base de acoplamiento?  
- Compruebe las relaciones de eventos Problemas del dispositivo y Micrófono. ¿Funcionaba el propio dispositivo correctamente?  
- Compruebe las relaciones de eventos de captura y representación del dispositivo que no funcionan.


Para obtener más información sobre las dimensiones y medidas disponibles en telemetría CQD, lea Dimensiones y [medidas disponibles en Panel](dimensions-and-measures-available-in-call-quality-dashboard.md)de calidad de llamadas.

Para el ruido de fondo, compruebe la relación del evento de silenciamiento para ver la duración del tiempo que los participantes se silenciaron.
 
Cree informes detallados en CQD y filtre en Id. de reunión para ver todos los usuarios y transmisiones de una reunión y agregar los campos que le interesan. Es posible que un usuario que informe del problema no sea el que estaba teniendo el problema. Solo están informando de la experiencia.
 
La telemetría no necesariamente resolverá el problema, pero puede ayudarle a comprender mejor dónde buscar e informar a sus decisiones. ¿Es la red, el dispositivo, el controlador o las actualizaciones de firmware, el uso o el usuario?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>¿Por qué veo hasta un 0,2 % de diferencia en los valores de llamadas y recuento de usuarios en las medidas y cómo obtener volúmenes más precisos? 

Para calcular las medidas de recuento de llamadas y recuento de usuarios, se realiza una operación countif distinta con los identificadores de llamada o de usuario del conjunto de datos. En conjuntos de datos grandes, hay un error de hasta un 0,2 % inherente a la operación countif distinta. Para obtener el volumen más preciso, debe basarse en las medidas de recuento de transmisiones, ya que no se basan en esta operación countif distinta. Filtrar para reducir el volumen de datos puede reducir el error, pero no puede eliminar esta fuente de error en diferentes recuentos de llamadas y usuarios. Consulte [Dimensiones y medidas disponibles en el Panel de](dimensions-and-measures-available-in-call-quality-dashboard.md) calidad de llamadas para qué medidas se verán afectadas.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>¿Por qué no puedo ver EUII en CQD?

Estos roles de administrador pueden obtener acceso a CQD, pero no pueden ver EUII (información de identificación del usuario final):

- Microsoft 365 de informes
- Teams de soporte técnico de comunicaciones

Para obtener más información sobre los roles que pueden tener acceso a CQD ,incluido EUII, lea Asignar roles para obtener acceso [a CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>¿Por qué veo Skype Empresarial en CQD cuando he filtrado para Teams solo?

Al filtrar por Teams solo en informes CQD (isTeams = 1), está  filtrando para todas las llamadas en las que se encuentra el primer punto de conexión Teams. Si el *segundo punto de* conexión Skype Empresarial, esa información se mostrará en el informe CQD.

CQDv2 y CQDv3 siempre tendrán recuentos totales diferentes, ya que CQDv3 tendrá nuevos escenarios que CQDv2 no tendrá. Por eso, comparar el total de resumen o los números totales agregados sin filtros tendrá estas diferencias esperadas.  

Según el escenario de los clientes, CQDv3 incluirá llamadas locales de SFB 2019 (si se usa SFB 2019 con un conector de datos), llamadas de bot de Skype (AA, CVI, VDI), Eventos en directo y llamadas RTC. Escenarios o características que están disponibles para los clientes, pero sus datos no están en CQD V2.

Por ejemplo, se espera que sus clientes y usted vean 200 000 transmisiones de audio, con 5000 errores en el informe de resumen CQD V2, frente a 300 000 transmisiones de audio con 5500 errores (procedentes de llamadas locales de 2019, llamadas CVI, llamadas RTC, y así sucesivamente) en CQD V3.

Para determinar si hay diferencias inesperadas, debe observar varios desgloses de los datos generales.  Comparar con la intención.  Cortar los datos mediante el par de categorías de agente de usuario es una de las primeras cosas que recomendamos.  *El primer producto* y *el segundo producto* también son buenas segmentaciones de datos.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas cuando sé que debería haber más entradas?

CQD está diseñado para consultas de datos resumidos y no está diseñado para la exportación de datos. Recomendamos que se restructuran los informes, siempre que sea posible, para evitar que se supere el límite de 10 000 filas. Empiece por ver sus KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, entre otras. Desde allí, puede explorar en profundidad las dimensiones de mayor cardinalidad. Tanto el Departamento de soporte técnico como Location-Enhanced informes proporcionan buenos ejemplos de este flujo de trabajo de exploración en profundidad.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>¿Por qué Wi-Fi conexiones VPN se muestran como cableadas en lugar de wi-fi?

Este es el comportamiento que se espera. El proveedor de VPN creó un adaptador ethernet virtual que se trata como una conexión por cable. Puesto que no está etiquetado correctamente, el sistema operativo no sabe que es una conexión Wi-Fi y la notifica como cableada.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>He activado la grabación basada en directivas en Teams y ahora las llamadas punto a punto se marcan como Conferencias, ¿qué ha ocurrido?

Este es el comportamiento esperado cuando la grabación basada en directivas está habilitada en Microsoft Teams. Grabación basada en directivas usa un bot Teams recorder implementado en Microsoft Azure para capturar el contenido de la reunión con fines de cumplimiento. Dado que un bot de grabadora es en sí mismo una parte de la llamada, la llamada ya no es punto a punto, sino una llamada de varias partes. Las llamadas de varias partes se clasifican como conferencias por Microsoft Teams, por lo que se indicarán como tales cuando vea estas llamadas en CQD y otras herramientas de calidad de llamadas.

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
