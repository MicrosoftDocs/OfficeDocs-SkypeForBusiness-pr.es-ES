---
title: Calidad de las llamadas uso llamar Analytics solucionar pobre Skype para empresas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "Utilizar detalles de llamar análisis sobre conectividad, redes y dispositivos para solucionar problemas de usuarios con Skype para llamadas de negocios y reuniones."
ms.openlocfilehash: 4f43c517beba318889e12fca8b09a488f6da5916
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Calidad de las llamadas uso llamar Analytics solucionar pobre Skype para empresas

Llamada Analytics le ayuda a solucionar problemas de conexión o llamada con Skype para el negocio. Llamada Analytics muestra información detallada acerca de los dispositivos, redes y conectividad de las llamadas y reuniones de cada usuario en su Skype para la cuenta de empresa. Si el edificio, del sitio y de inquilinos se ha agregado información al llamar a Analytics, también se mostrará para cada llamada y sesión. Información disponible a través de llamar Analytics puede ayudar a averiguar por qué un usuario tenía una llamada deficiente o experiencia de reunión. 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar problemas de calidad de llamada utilizando Analytics llamar

El nivel de permisos asignado a usted determina qué tipo de información tiene acceso a en llamar Analytics:
  
- **Skype para Business admin**: tendrá acceso a toda la información en llamar a Analytics y en el Skype para el centro de administración de negocios.
    
- **Agente de asistencia técnica con permisos de nivel 1**: vea un conjunto limitado de datos en Analytics llamar. Puede solucionar problemas de las llamadas, pero le entrega problemas con reuniones a un agente de nivel 2. No tiene acceso al resto de la Skype para el centro de administración de negocios.
    
- **Agente de asistencia técnica con permisos de nivel 2**: ver todos los datos disponibles en llamar a Analytics y puede ayudar a solucionar problemas relacionados con llamadas y reuniones. No tiene acceso al resto de la Skype para el centro de administración de negocios.
    
Consulte su Skype para Business admin si necesita ayuda con los permisos.
  
 **Abrir llamar Analytics como un agente de asistencia de nivel 1 o nivel 2**
  
1. Ir al centro de administración de Office 365 e inicie sesión con su cuenta de trabajo o escuela. A continuación, en el explorador web vaya a *https://adminportal.services.skypeforbusiness.com*.
    
2. En **La búsqueda de usuarios**, empiece a escribir la dirección o el nombre o el sip del usuario cuyas llamadas que desee solucionar y, a continuación, seleccione el usuario de la lista.
    
    ![Captura de pantalla del cuadro de búsqueda de usuarios de Analytics llamar en el Skype para el centro de administración de negocios.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. En el **historial de llamadas**, seleccione la llamada o reunión que desee solucionar.
    
    ![Captura de pantalla muestra la página de historial de llamadas para un usuario con información como detalles de contacto del usuario, un resumen de la calidad de 7 días y la actividad de llamadas y reuniones y un resumen de las fechas y horas, destinatarios y calidad de audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Seleccione la ficha **Avanzadas** y, a continuación, busque elementos de amarillos y rojos que indican la llamada mala calidad o problemas de conexión.
    
    En los detalles de la sesión de cada llamada o una reunión, problemas de poca importancia aparecen en amarillo. (Por ejemplo, en la siguiente captura de pantalla, los valores son en color amarillo para variación promedio, variación máxima y tasa de pérdida de paquetes promedio.) Si algo es amarillo, está fuera del intervalo normal y podría estar contribuyendo al problema, pero es poco probable que la causa principal del problema. Si algo es rojo, es un problema importante, y es probable que la causa principal de la calidad de las llamadas deficiente para esta sesión. 
    
    ![Captura de pantalla muestra la ficha Opciones avanzadas del historial de llamadas de un usuario con la sección de red entrantes expandida para mostrar que los datos de variación promedio, variación máxima y tasa de pérdida de paquetes promedio se muestran en un color amarillo, lo que significa que son problemas de poca importancia.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
En raras ocasiones, no recibe la calidad de los datos de la experiencia para sesiones de audio. A menudo esto se debe a la eliminación de llamada y la conexión con el cliente termina. Cuando esto ocurre, la clasificación de la sesión es "no disponible".
  
Para las sesiones de audio con calidad de experiencia (QoE) datos, la tabla siguiente describe los principales problemas que califican una sesión como "pobre".
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Configuración de llamada  <br/> |Sesión  <br/> |El código de error Ms-diag 20-29 indica error en la configuración de la llamada. El usuario no pudo unirse a la llamada o reunión.  <br/> |
|Audio red clasificada llamada deficiente  <br/> |Sesión  <br/> |Problemas de calidad de la red se encontraron en áreas como la pérdida de paquetes, vibración, degradación NMOS, RTT, u ocultan la relación. Para obtener más información acerca de las condiciones utilizadas para clasificar las llamadas deficientes, consulte este [blog de Microsoft registra](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no está funcionando correctamente. Dispositivo no funciona proporciones es: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>See also
[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

