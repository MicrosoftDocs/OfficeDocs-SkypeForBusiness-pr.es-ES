---
title: Preguntas más frecuentes (P+F) sobre el panel de calidad de llamadas
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lea las preguntas más frecuentes (P+F) y las respuestas sobre el panel de calidad de llamadas (CQD) de Microsoft Teams.
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110263"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F) sobre el panel de calidad de llamadas

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

[¿Por qué el CQD marca una llamada como "Buena" si uno o más participantes de la reunión tenían una experiencia deficiente?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[¿Por qué veo una diferencia de hasta un 0,2 % en el número de llamadas y usuarios de las medidas y cómo obtener volúmenes más precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[¿Por qué los datos del CQD de Skype Empresarial son distintos de los datos del CQD de Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[¿Por qué no puedo ver EUII en el CQD?](#why-cant-i-see-euii-in-cqd)

[¿Por qué veo información de Skype Empresarial en el CQD cuando he filtrado solo para Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas si sé que debería haber más entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>¿Por qué el CQD marca una llamada como "Buena" si uno o más participantes de la reunión tenían una experiencia deficiente?

Consulte las reglas que el CQD usa para la clasificación [de la transmisión.](stream-classification-in-call-quality-dashboard.md)
 
Para las transmisiones de audio, cualquiera de los 5 clasificadores, que se calcula para el promedio según la longitud de la llamada, podría estar todo dentro de parámetros "buenos". No significa que los usuarios no experimentaron algo que haya contribuido a una salida de audio, estática o problemas. 

Para determinar si se trataba de un problema de red, mire el delta entre los valores promedio de la sesión y los valores máximos. Los valores máximos son el máximo detectado y notificado durante la sesión.
 
Este es un ejemplo de cómo solucionar esta situación. Supongamos que hace un seguimiento de red durante una llamada y los primeros 20 minutos no se pierden paquetes, pero después hay un intervalo de 1,5 segundos de paquetes y, a continuación, es bueno para el resto de la llamada. El promedio será del <del 10 % (0,1) de pérdida de paquetes incluso en un análisis RTP de seguimiento de Wireshark. ¿Cuál fue la pérdida máxima de paquetes? 1,5 segundos en un período de 5 segundos serían 30% (0,3). ¿Esto ocurrió dentro del período de muestreo de cinco segundos (quizás, podría dividirse en el período de muestreo)?
 
Si las métricas de red tienen un buen aspecto en los valores promedios y máximos, busque otros datos de telemetría: 
- Compruebe la relación de eventos insuficiente de la CPU para ver si los recursos de CPU detectados eran insuficientes y estaban provocando mala calidad. 
- ¿El dispositivo de audio estaba en el modo Dúplex medio para evitar comentarios debido a micrófonos que se acercan a los altavoces? 
- Compruebe la relación de evento AEC a doble cara del dispositivo. ¿El dispositivo tenía problemas o el micrófono causaba ruido o problemas estáticos debido a fallos de audio USB al conectarse a un hub o a una base de acoplamiento?  
- Compruebe las relaciones de eventos de problemas de dispositivo y micrófono. ¿Estaba funcionando correctamente el dispositivo?  
- Compruebe las relaciones de eventos del dispositivo de captura y representación que no son funcionales.


Para obtener más información sobre las dimensiones y medidas disponibles en telemetría del CQD, lea dimensiones y medidas disponibles en el panel de calidad [de llamadas.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Para el ruido de fondo, compruebe la relación de silenciar el evento para ver la cantidad de tiempo que los participantes han estado silenciados.
 
Cree informes detallados en el CQD y filtre en Id. de reunión para ver todos los usuarios y las transmisiones de una reunión y agregar los campos que le interesen. Puede que un usuario que informe del problema no sea el que estaba teniendo el problema. Solo están informando de la experiencia.
 
La telemetría no mostrará necesariamente el problema, pero puede ayudarle a comprender mejor dónde buscar e informar sobre sus decisiones. ¿Es de red, dispositivo, controlador o actualizaciones de firmware, uso o usuario?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>¿Por qué veo una diferencia de hasta un 0,2 % en el número de llamadas y usuarios de las medidas y cómo obtener volúmenes más precisos? 
Para calcular el recuento de llamadas y las medidas del recuento de usuarios, se realiza una operación countif distinta a los identificadores de llamada o de usuario del conjunto de datos. En conjuntos de datos de gran tamaño, hay un error de hasta un 0,2 % inherente con la operación Countif distinta. Para obtener el volumen más preciso, debe basarse en las medidas de recuento de transmisiones, ya que no se basan en esta distinta operación countif. Filtrar para reducir el volumen de datos puede reducir el error, pero es posible que no elimine este origen de errores en distintos recuentos de llamadas y usuarios. Consulte dimensiones [y medidas disponibles en el panel de](dimensions-and-measures-available-in-call-quality-dashboard.md) calidad de llamadas para saber qué medidas se verán afectadas.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>¿Por qué los datos del CQD de Skype Empresarial son distintos de los datos del CQD de Teams? 


> [!IMPORTANT]
> Desde el 1 de julio de 2020, el antiguo CQD (CQD.lync.com) usa los datos del último CQD (CQD). Teams.microsoft.com). Los datos antiguos del CQD ya no están disponibles y no puede exportar los datos de creación o informe. Aún puede usar CQD.lync.com (disponible en el Centro de administración de Skype Empresarial), pero desactivaremos el acceso a CQD.lync.com próximamente, por lo que debe moverse al CQD. Teams.microsoft.com si aún no lo ha hecho.


Si intenta comparar datos entre el CQD antiguo del portal heredado de Skype Empresarial (cqd.lync.com) y el último CQD del Centro de administración de Teams (cqd.teams.microsoft.com), verá que los datos no coinciden. Esto se debe a que los informes del CQD más recientes sobre muchos escenarios de llamadas adicionales. Si todavía usa informes del CQD anterior, consulte este artículo para interpretar dichos informes: Panel de calidad de llamadas [para Skype Empresarial Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>¿Por qué no puedo ver EUII en el CQD?

Estos roles de administrador pueden acceder al CQD, pero no pueden ver EUII (información de identificación del usuario final):
- Lector de informes de Microsoft 365
- Especialista de soporte técnico de comunicaciones de Teams

Para obtener más información sobre los roles que pueden tener acceso al CQD , incluida EUII, lea Asignar [roles para acceder al CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>¿Por qué veo información de Skype Empresarial en el CQD cuando he filtrado solo para Teams?

Cuando se filtra por Teams solo en informes del CQD (isTeams = 1), se filtran todas las llamadas en las que el primer punto de *conexión* es Teams. Si el *segundo punto de* conexión es Skype Empresarial, esa información aparecerá en el informe del CQD.

CQDv2 y CQDv3 siempre tendrán recuentos totales diferentes, ya que CQDv3 tendrá nuevos escenarios que no tendrán CQDv2. Por eso, comparar los números de resumen totales o totales agregados sin filtros tendrá estas diferencias esperadas.  

Según el escenario de clientes, el CQDv3 incluirá llamadas locales de SFB 2019 (si se usa SFB 2019 con un conector de datos), llamadas de bot de Skype (AA, CVI, VDI), eventos en directo y llamadas RTC. Escenarios o características que están disponibles para los clientes, pero sus datos no están en CQD V2.

Por ejemplo, se espera que sus clientes y usted vean 200 000 transmisiones de audio, con 5000 errores en el informe de resumen CQD V2; frente a 300 000 transmisiones de audio con 5500 errores (procedentes de llamadas locales de 2019, llamadas CVI, llamadas RTC, etc.) en el CQD V3.

Para determinar si hay diferencias inesperadas, debe observar varios desgloses de los datos generales.  Compare con intención.  Cortar los datos por User Agent Category Pair es una de las primeras cosas que recomendamos.  *First Product* and *Second Product* are also good slicers.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>¿Por qué mis informes personalizados solo devuelven un máximo de 10 000 filas si sé que debería haber más entradas?

El CQD está diseñado para consultas de datos resumida y no está diseñado para la exportación de datos. Le recomendamos que valore sus informes cuando sea posible para evitar que se supere el límite de 10 000 filas. Empiece observando los KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, etc. Desde allí, puede explorar en profundidad las dimensiones de mayor cardinalidad. El departamento de soporte técnico y Location-Enhanced informes proporcionan buenos ejemplos de este flujo de trabajo de obtención de detalles.

## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
