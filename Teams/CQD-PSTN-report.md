---
title: Usar el informe enrutamiento directo de RTC del CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Use el informe Enrutamiento directo de RTC del Panel de calidad de llamadas (CQD) de Microsoft Teams para supervisar y solucionar problemas de llamadas RTC en Microsoft Teams.
ms.openlocfilehash: 7b7205658358cfa3aa90824718c03731fa33a534
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270715"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Usar el informe enrutamiento directo de RTC del CQD

El informe Enrutamiento directo de RTC del Panel de calidad de llamadas (CQD) de Microsoft Teams está disponible en nuestras plantillas de consulta descargables de [Power BI para el CQD](https://www.microsoft.com/download/details.aspx?id=102291). 


El informe Enrutamiento directo de RTC del CQD (Informe de enrutamiento directo de RTC.pbit) le ayuda a comprender los patrones de uso y la calidad de los servicios RTC. Use este informe para supervisar el uso del servicio, información sobre el controlador de borde de sesión (SBC), el servicio de telefonía, los parámetros de red y los detalles de la relación de eficacia de la red. Esta información puede ayudarle a identificar problemas, incluido el motivo de las llamadas caídas. Por ejemplo, podrás ver cuándo se baja el volumen o cuántas llamadas se ven afectadas y por qué.


El informe de enrutamiento directo de RTC del CQD tiene cuatro secciones:

  - [Información general sobre RTC](#pstn-overview)

  - [Detalles del servicio](#service-details)

  - [Relación de eficacia de red](#network-effectiveness-ratio)

  - [Parámetros de red](#network-parameters)

## <a name="highlights"></a>Resúmenes

1. Analizar por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada

   El informe Enrutamiento directo de RTC del CQD agrega métricas de confiabilidad y uso para todos los SBC de su inquilino para los últimos 7, 30 o 180 días (6 meses). Puede analizar datos por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada. Si está interesado en un determinado SBC o país, podrá identificar cambios en las tendencias en el intervalo de tiempo seleccionado.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de pantalla de los filtros disponibles en el informe enrutamiento directo de RTC del CQD.":::
   
2. Realizar un seguimiento de las tendencias

    El análisis de tendencias es esencial al intentar comprender el uso y la confiabilidad del servicio. Las tendencias horarias ofrecen una vista cercana del rendimiento diario, lo que ayuda a identificar incidentes en tiempo real. Las tendencias diarias le permiten ver el estado del servicio desde una perspectiva a largo plazo. Es importante poder desplazarse entre esos dos modos con granularidad de datos adecuada. El informe Enrutamiento directo de RTC del CQD proporciona información general de tendencias de 6 meses, tendencias diarias de 7 y 30 días y tendencias horarias para que pueda analizar el rendimiento en cada nivel.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de pantalla de gráficos de tendencias en el informe enrutamiento directo de RTC del CQD.":::

3. Explorar en profundidad hasta el nivel de usuario o SBC

   Hemos estado creando capacidades de obtención de detalles en muchas categorías de datos del CQD, lo que le permite comprender rápidamente el uso o la distribución de confiabilidad en el nivel de SBC o usuario. Al usar la exploración en profundidad, puede consultar rápidamente los problemas y comprender el impacto real del usuario. El informe enrutamiento directo RTC del CQD incluye información detallada sobre las métricas de detalles del servicio y relación de efectividad de la red. Haga clic en el punto de datos que le interesa para explorar en profundidad los detalles de SBC o a nivel de usuario.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de pantalla que muestra la funcionalidad de obtención de detalles en un punto de datos.":::


## <a name="pstn-overview"></a>Información general sobre RTC

El Informe de enrutamiento directo de RTC del CQD proporciona la siguiente información relacionada con el estado general del servicio de los últimos 180 días.
![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report1.png)

Por ejemplo, si le interesa el uso y el mantenimiento general de todas las llamadas entrantes que pasan por SBC abc.bca.adatum.biz con Estados Unidos como país interno:

| **Llamar** | **Descripción**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Puede usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com como controlador de panel de sesión y Estados Unidos como país interno. |
| 2            | Tendencia de uso de los últimos 180 días. Puedes encontrar el informe de detalles de uso en la página Detalles del servicio.                                                                     |
| 3            | Tendencia posterior al retraso de marcado, latencia, vibración y pérdida de paquetes de los últimos 180 días. Puede encontrar un informe detallado en la página Parámetros de red.                           |
| 4            | Tendencia de llamadas simultáneas y usuario activo diario de los últimos 180 días. Este gráfico puede ayudarle a comprender el volumen máximo del servicio.                            |
| 5            | El motivo de finalización de llamada más importante afectó la calidad del servicio durante los últimos 180 días. Puedes encontrar detalles del estado del servicio en la página Network Effective Ratio(NER).                    |

## <a name="service-details"></a>Detalles del servicio

Esta página proporciona tendencias de uso del servicio por día y un desglose de los comentarios de los usuarios por geografía.

  - **Total de llamadas de intento:** Total de llamadas de intentos en ese intervalo de tiempo, incluidas las llamadas correctas y las que no se realizaron correctamente

  - **Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo

  - **Minutos totales:** Uso total de minutos en ese intervalo de tiempo

  - **Usuarios activos diarios (DAU) –** Recuento de usuarios activos diarios que realizaron al menos una llamada conectada en ese día

  - **Llamadas simultáneas:** Número máximo de llamadas activas simultáneas en un minuto

  - **Comentarios del usuario:** La puntuación "Calificar mi llamada" proviene del usuario. 3-5 se considera una buena llamada. 1-2 se considera una mala llamada.

![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report2.png)

Por ejemplo:

1.  Si ve que la duración media de la llamada baja a 0 a 14/02/2020, primero puede comprobar si el volumen de la llamada parece normal y ver si hay una gran discrepancia entre el total de llamadas de conexión y el total de llamadas de intentos. A continuación, vaya a la página Network Effectiveness Ratio para invertir en razones de fallo de llamada.

2.  Si ve puntos rojos crecientes en el mapa de comentarios de los usuarios, puede ir a las páginas Relación de efectividad de red y Parámetro de red para ver si hay anomalías y podría elevar un ticket con MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Relación de eficacia de red

Esta es la misma métrica que aparece en el panel Mantenimiento general. Puede comprobar el número NER cada hora con los detalles de las llamadas afectadas para ver las direcciones de llamada (entrantes y salientes) en la relación de efectividad de la red horaria y el motivo de finalización de la llamada que se muestra a continuación.

  - **NER** - La capacidad (%) de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas enviadas a un destinatario.

  - **Código de respuesta SIP**: un código de respuesta entero de tres dígitos muestra el estado de la llamada.

  - **Código de respuesta de Microsoft**: código de respuesta A enviado desde el componente de Microsoft.

  - **Descripción** : la fase de motivo que se corresponde con el código de respuesta SIP y el código de respuesta de Microsoft.

  - **Número de llamadas afectadas** : el número total de llamadas se ha visto afectado durante el intervalo de tiempo seleccionado.

> ![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report3.png)
> 
Por ejemplo:

![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report4.png)

Si Daily NER tiene una caída el 05/02/2020, puede hacer clic en la fecha y otros gráficos se acercarán a esa fecha específica.

![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report5.png)

A partir de la tendencia NER Buen porcentaje por hora, puede encontrar la caída ocurre alrededor de las 21:00. A continuación, haga clic de nuevo para ampliar a la hora 21 y active Detalles de llamadas con efectos para ver cuántas llamadas han fallado en esa hora y cuáles son las razones de finalización de la llamada. Puede comenzar con la toma de problemas de sí mismo en cualquier problema de SBC o informar a Service Desk si el problema no está relacionado con SBC.

## <a name="network-parameters"></a>Parámetros de red

Todos los parámetros de red se miden desde la interfaz de enrutamiento directo hasta el controlador de borde de sesión. Para obtener información sobre los valores recomendados, vea [Preparar la red de su organización para Microsoft Teams](prepare-network.md) y vea los valores recomendados de Customer Edge a Microsoft Edge.

  - **Vibración** : es la medida en milisegundos de la variación en el tiempo de retraso en la propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).

  - **Pérdida de paquetes** : es una medida del paquete que no ha podido llegar; se calcula entre dos puntos de conexión.

  - **Latencia** : (también conocido como tiempo de ida y vuelta) es el período de tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse la señal. Este retardo de tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.

> ![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report6.png)

Por ejemplo:

Si ve un pico en cualquiera de los cuatro gráficos (Latencia, Vibración, Tasa de pérdida de paquetes, Retraso posterior al marcado) para una fecha específica, por ejemplo, Latencia en 14/02/2020, haga clic en el punto de fecha. Y el gráfico de tendencia por hora de la parte inferior se actualizará para mostrar el número por hora. Puede comprobar los SBCs o levantar un ticket con MS Service Desk.

![Captura de pantalla: Informe del CQD de RTC.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Temas relacionados

[Usar Power BI para analizar datos del CQD para Microsoft Teams](CQD-PSTN-report.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
