---
title: Calidad de las llamadas análisis de uso de llamadas para solucionar problemas de Skype deficiente para la empresa
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
description: Use llamar análisis obtener información detallada sobre los dispositivos, redes y conectividad para solucionar los problemas de los usuarios con Skype para reuniones y llamadas de trabajo.
ms.openlocfilehash: cb887a1c582c9547616c2133c2f175ac634e2da8
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Calidad de las llamadas análisis de uso de llamadas para solucionar problemas de Skype deficiente para la empresa

Análisis de llamada le ayuda a solucionar los problemas de conexión o llamada con Skype para la empresa. Análisis de la llamada muestran información detallada acerca de los dispositivos, redes y conectividad para las llamadas y las reuniones de cada usuario en su Skype para la cuenta de empresa. Si crear, del sitio y de inquilinos se ha agregado información para análisis de llamadas, también se mostrarán para cada llamada y la sesión. Información disponible a través de análisis de llamadas puede ayudar a averiguar por qué un usuario tuvo una llamada deficiente o experiencia de reunión. 
  
> [!NOTE]
> Análisis de la llamada está actualmente en la vista previa. Texto e imágenes que se describen aquí no pueden coincidir con su experiencia.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar los problemas de calidad de llamada mediante el análisis de llamadas

El nivel de permisos que se le han asignado determina qué tipo de información tiene acceso a llamar análisis de:
  
- **Skype para administración empresarial**: tener acceso a toda la información en análisis de llamadas y en el Skype para el centro de administración de negocio.
    
- **Agente de departamento de soporte técnico con permisos de nivel 1**: vea un conjunto limitado de datos de análisis de llamadas. Puede solucionar problemas de las llamadas, pero podrá entregar problemas con las reuniones a un agente de nivel 2. No tiene acceso al resto de la Skype para el centro de administración de negocio.
    
- **Agente de departamento de soporte técnico con permisos de nivel 2**: vea todos los datos disponibles en análisis de llamadas y puede ayudar a solucionar los problemas con las llamadas y las reuniones. No tiene acceso al resto de la Skype para el centro de administración de negocio.
    
Si necesita ayuda con los permisos, vea su Skype para administración empresarial.
  
 **Análisis de llamar Open como un agente de departamento de soporte técnico de nivel 1 o nivel 2**
  
1. Vaya al centro de administración de Office 365 e iniciar sesión con su cuenta de trabajo o escuela. A continuación, en el explorador web vaya a *https://adminportal.services.skypeforbusiness.com*.
    
2. En la **Búsqueda de usuarios**, empiece a escribir el nombre o el sip dirección del usuario cuyas llamadas que desea solucionar problemas y, a continuación, seleccione el usuario en la lista.
    
    ![Captura de pantalla del cuadro de búsqueda de usuarios del análisis de llamadas en la Skype para el centro de administración de negocio.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. En el **historial de llamadas**, seleccione la llamada o reunión que va a solucionar problemas.
    
    ![Captura de pantalla muestra la página de historial de llamadas para un usuario con información como detalles de contacto del usuario, un resumen de la actividad para las reuniones y las llamadas y calidad de 7 días e información general de las fechas y horas, destinatarios y una calidad de audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Seleccione la ficha **Opciones avanzadas** y, a continuación, busque elementos de amarillos y rojos que indican problemas de calidad o conexión llamada deficiente.
    
    En los detalles de la sesión para cada llamada o una reunión, problemas secundarias aparecen en amarillo. (Por ejemplo, en la siguiente captura de pantalla, los valores están en amarillo para vibración Media, la vibración de Max y la frecuencia de pérdida de paquetes promedio.) Si algo es el amarillo, está fuera del intervalo normal y puede contribuir al problema, pero es poco probable que sea la causa principal del problema. Si algo es rojo, es un problema importante, y es probable que es la causa principal de la calidad de llamadas deficientes para esta sesión. 
    
    ![Captura de pantalla muestra la ficha Avanzadas del historial de llamadas de un usuario con la sección de red entrantes expandida para mostrar que se muestran los datos de vibración Media, Vibración máxima y tasa de pérdida de paquetes Media en un color amarillo, lo que significa que son secundarias problemas.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
En algunos casos poco frecuentes, no se recibió calidad de experiencia de datos para las sesiones de audioconferencias. A menudo esto está causado por la llamada quitando y la conexión con el cliente de terminación. Cuando esto ocurre, la clasificación de la sesión es "no disponible".
  
Para las sesiones de audioconferencias que tienen la calidad de los datos de la experiencia (QoE), en la siguiente tabla se describe los problemas principales que calificar una sesión como "malo".
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Programa de instalación de la llamada  <br/> |Sesión  <br/> |El código de error de que MS-diag 20-29 indica el error en la configuración de la llamada. El usuario no puede unirse a la llamada o reunión.  <br/> |
|Red audio clasificados llamada deficiente  <br/> |Sesión  <br/> |Problemas de calidad de red se han producido en áreas como la pérdida de paquetes, vibración, degradación de NMOS, RTT, u ocultan relación. Para obtener más información acerca de las condiciones que se usan para clasificar las llamadas deficientes, vea esta [entrada de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no está funcionando correctamente. Dispositivo no funciona proporciones es: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>See also
[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Análisis de llamada y el panel de calidad de llamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 