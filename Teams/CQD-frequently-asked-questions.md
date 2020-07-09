---
title: Panel de calidad de llamadas (el CQD) preguntas más frecuentes (FAQ)
ms.author: lolaj
author: LolaJacobsen
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
description: Lea las preguntas más frecuentes (FAQ) y las respuestas acerca del panel de calidad de llamadas de Microsoft Teams (CQD).
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086176"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Panel de calidad de llamadas (el CQD) preguntas más frecuentes (FAQ)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

[¿Por qué el CQD marca una llamada como "buena" si uno o más participantes de la reunión tuvieran una experiencia deficiente?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[¿Por qué veo una diferencia de 0,2% en los valores de llamadas y usuarios recuentos de las medidas y cómo obtener los volúmenes más precisos?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[¿Por qué la apariencia de los datos del informe de CQD V2 es diferente de la de los datos del informe del CQD V3?](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[¿Por qué diferencia los datos del CQD de Skype empresarial de los datos del CQD de Teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[¿Por qué no puedo ver EUII en el CQD?](#why-cant-i-see-euii-in-cqd)

[¿Por qué veo la información de Skype para empresas en el CQD cuando he filtrado solo para equipos?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>¿Por qué el CQD marca una llamada como "buena" si uno o más participantes de la reunión tuvieran una experiencia deficiente?

Consulta las reglas que usa el CQD para la [clasificación de secuencias](stream-classification-in-call-quality-dashboard.md).
 
En el caso de las transmisiones de audio, cualquiera de los cinco clasificadores, que se calculan para el promedio en función de la duración de la llamada, pueden estar dentro de los parámetros "buenos". No significa que los usuarios no tengan algo que haya contribuido a un problema de salida de audio, como estático o en un problema. 

Para determinar si ha habido un problema de red, mire la diferencia entre los valores promedio de la sesión y los valores máximos. Los valores máximos son los máximos detectados y notificados durante la sesión.
 
Este es un ejemplo de cómo solucionar esta situación. Supongamos que realiza un seguimiento de la red durante una llamada y los primeros 20 minutos no se pierden paquetes, pero después tiene un intervalo de 1,5 segundos de paquetes y, después, bueno durante el resto de la llamada. El promedio se va a <pérdida de paquetes del 10% (0,1) incluso en un análisis RTP de seguimiento de Wireshark. ¿Cuál fue la pérdida máxima de paquetes? 1,5 segundos en un período de 5 segundos sería el 30% (0,3). ¿Eso se produjo dentro del período de muestreo de cinco segundos (tal vez o podría dividirse durante el período de muestreo)?
 
Si la métrica de red se ve bien en los valores máximos y promedio, busque otros datos de telemetría: 
- Compruebe la proporción insuficiente de eventos de CPU para ver si los recursos de la CPU detectados no eran suficientes y producían una mala calidad. 
- Era el dispositivo de audio en modo dúplex medio para evitar recibir comentarios causados por micrófonos que se encuentran cerca de los altavoces. 
- Compruebe la proporción de eventos de AEC dúplex medio de un dispositivo. Fue el problema del dispositivo o el problema de micrófono introdujo ruido o estático debido a las desprotecciones de audio USB al estar conectado a un concentrador o una estación de acoplamiento:  
- Verifique las relaciones de los problemas del dispositivo y los problemas del micrófono. ¿El dispositivo funcionaba correctamente?  
- Compruebe que las relaciones de eventos de la captura y el dispositivo de representación no funcionan.


Para obtener más información sobre las dimensiones y medidas disponibles en la telemetría del CQD, lea [dimensiones y medidas disponibles en el panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

En ruido de fondo, Compruebe la proporción de eventos de silencio para ver la cantidad de tiempo que los participantes estaban silenciados.
 
Cree informes detallados en el CQD y filtre por el identificador de la reunión para ver todos los usuarios y las secuencias de una reunión y agregue los campos que le interesen. Es posible que un usuario que informa del problema no sea el que tenía el problema. Se reportan únicamente a la experiencia.
 
La telemetría no reconocerá el problema, pero puede ayudarlo a comprender mejor dónde mirar e informar de las decisiones. ¿Hay actualizaciones, uso o usuario de la red, el dispositivo, el controlador o el firmware?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>¿Por qué veo una diferencia de 0,2% en los valores de llamadas y usuarios recuentos de las medidas y cómo obtener los volúmenes más precisos? 
Para calcular el número de llamadas y las medidas de recuento de usuarios, se realiza una operación de resume distinta en la llamada o en los identificadores de usuario del conjunto de datos. En conjuntos de datos grandes, existe un error de hasta 0,2% inherente a la operación DISTINCT contar.Si. Para obtener el volumen más preciso, debe basarse en las medidas de recuento de flujo porque no dependen de esta operación diferenciada de contar.Si. El filtrado para reducir el volumen de datos puede reducir el error, pero no puede eliminar esta fuente de error en distintos números de llamadas y usuarios. Consulte las [dimensiones y medidas disponibles en el panel de calidad](dimensions-and-measures-available-in-call-quality-dashboard.md) de las llamadas para las que se ven afectadas las medidas.

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>¿Por qué la apariencia de los datos del informe de CQD V2 es diferente de la de los datos del informe del CQD V3? 

Si ve diferencias de datos entre el CQD versión 2 y el V3, asegúrese de que la comparación o validación de datos se realiza en un nivel de "Apple to-manzanas" y en un nivel estrecho, no en un nivel agregado. Por ejemplo, si filtra los informes de MSIT ' crear 30 ' datos de cliente de escritorio de WiFi Teams, el porcentaje de mala calidad debe ser el mismo entre V2 y V3.

La clasificación CQDv2 para llamada error solo se tiene en cuenta para el "audio" modal, en CQDv3 esta clasificación se produce para cada modalidad (audio, vídeo y uso compartido) y se representa en el flujo de moda respectivo. 

Para Teams, CQDv2 aplica los mismos comentarios de los usuarios a todas las modalidades CQDv3 aplica la base de comentarios para la modalidad de los equipos.

El CQD V3 incluye 
1. Llamadas de 2019 de Skype empresarial Server, 
2. Llamadas de Skype bot, como: operador automático, cola de llamadas, servicio de anuncio de conferencia, 
3. Interfaz de escritorio virtual,
4. Interoperabilidad de videoconferencias
3. Llamadas de Publisher y moderador de eventos en vivo, y 
4. Llamadas RTC. 

Para obtener información sobre cómo usar estas plantillas de Power BI para analizar y notificar los datos del CQD, lea [usar Power BI para informes de CQD](cqd-power-bi-query-templates.md).


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>¿Por qué diferencia los datos del CQD de Skype empresarial de los datos del CQD de Teams? 


> [!IMPORTANT]
> A partir del 1 de julio de 2020, el CQD anterior accede a los datos desde el CQD más reciente. Los datos anteriores del CQD ya no están disponibles y no puede exportar los datos de compilación o de informe.


Si está intentando comparar datos entre el CQD anterior del portal heredado de Skype empresarial (cqd.lync.com) y el último CQD del centro de administración de equipos (cqd.teams.microsoft.com), podrá advertir rápidamente que los datos no coinciden. Esto se debe a que los últimos informes de CQD sobre muchos escenarios de llamadas adicionales. Si todavía está usando informes del CQD anterior, use este artículo para que le ayude a interpretar esos informes: [Panel de calidad de llamadas para Skype empresarial Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).



Este es un ejemplo de cómo se aplican filtros específicos para comparar los datos del CQD V2 y el CQD V3:

1. Registro de calidad de la calidad disponible = verdadero

2. Filtro agregar es un par de servidores con valor: cliente: cliente y cliente: servidor. La mayoría de los inquilinos prefieren excluir las llamadas de servidor: servidor.

3. Agregar un filtro para la categoría de agente de usuario y filtrar el operador automático, cola de llamadas, Bot, sistema de salas, MediationServer, servicio de anuncio de conferencia, VDI, etc.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="Captura de pantalla de la aplicación de filtros específicos en el CQD V3":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="Captura de pantalla de la aplicación de filtros específicos en el CQD versión 2":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Otras diferencias previstas entre el CQD y el CQD V3

Para obtener más información sobre las diferencias entre el CQD más antiguo y el más reciente, lea el blog sobre el [Panel de calidad de llamadas avanzada](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) , del 5 de noviembre de 2019.


> [!IMPORTANT]
> A partir del 1 de julio de 2020, el CQD anterior accede a los datos desde el CQD más reciente. Los datos anteriores del CQD ya no están disponibles y no puede exportar los datos de compilación o de informe.

Probablemente verá más diferencias de datos entre los informes de CQD más antiguos y más recientes en el nivel sumado o en el resumen. Si compara los datos en un nivel más granular, obtendrá una comparación "entre manzanas". Por ejemplo, si está buscando los datos de un edificio individual, el porcentaje de calidad deficiente debe ser el mismo entre el antiguo y el nuevo informe de CQD.

- Elija un escenario con un enfoque estrecho, como conexiones corporativas por cable, equipos de escritorio de Windows o una sola región o edificio.
- Compruebe los intervalos de IP de los equipos MR, TR o MP. Los intervalos de equipos son más recientes que los de Skype empresarial online, y pueden provocar problemas de conectividad relacionados con los firewalls.
- No compare los números de resumen o de nivel superior. Estas comparaciones le llevarán a comparar una gran cantidad de llamadas de Skype empresarial online en una conexión de cable corporativa con un pequeño volumen de llamadas de equipo en una red de LTE o privada.
- Tenga cuidado con el sesgo de la ubicación y las diferencias de población: existen muchas comparaciones que son demasiado diferentes para ser útiles:
  - NOAM: APAC
  - NY: Goa
  - Con cable: WiFi
  - Red corporativa: red doméstica
  
### <a name="why-cant-i-see-euii-in-cqd"></a>¿Por qué no puedo ver EUII en el CQD?

Estos roles de administrador pueden acceder al CQD, pero no pueden ver la información de identificación de EUII (información identificable por el usuario final):
- Lector de informes de Microsoft 365
- Especialista de soporte técnico de comunicaciones de Teams

Para obtener más información sobre los roles que pueden obtener acceso al CQD, incluyendo EUII-Read, [asigne roles para acceder al CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>¿Por qué veo la información de Skype para empresas en el CQD cuando he filtrado solo para equipos?

Al filtrar por equipos solo en informes de CQD (isTeams = 1), está filtrando todas las llamadas en las que el *primer punto de conexión* sea equipos. Si el *segundo punto de conexión* es Skype empresarial, esa información se mostrará en el informe de CQD.

CQDv2 y CQDv3 siempre tendrán diferentes recuentos totales porque CQDv3 tendrá nuevos escenarios que CQDv2 no tendrá. Por eso, la comparación de números totales o totales agregados sin filtros tendrá estas diferencias previstas.  

Según el escenario de los clientes, CQDv3 incluirá llamadas locales de SFB 2019 (si SFB 2019 se usa con un conector de datos), llamadas de Skype Bot (AA, CVI, VDI), eventos en vivo y llamadas RTC. Escenarios/características que están disponibles para los clientes, pero sus datos no están en el CQD V2.

Por ejemplo, se espera que sus clientes vean las transmisiones de audio de 200.000, con errores de 5000 en el informe Resumen de CQD V2. en comparación con las transmisiones de audio de 300.000 con errores de 5500 (provenientes de 2019 llamadas locales, llamadas de CVI, llamadas RTC, etc.) en el CQD V3.

Para determinar si hay alguna diferencia inesperada, debe tener en cuenta los diversos desgloses de los datos generales.  Comparar con el intento.  Segmentar los datos por pareja de categoría de agente de usuario es una de las primeras cosas que recomendamos.  El *primer producto* y el *segundo producto* también son buenos segmentadores.  


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)