---
title: "Calidad de llamadas de análisis de uso llamar a solucionar problemas de una mala Skype para la empresa"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# Calidad de llamadas de análisis de uso llamar a solucionar problemas de una mala Skype para la empresa

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](66945036-ae87-4c08-a0bb-984e50d6b009.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/66945036-ae87-4c08-a0bb-984e50d6b009). 
  
Análisis de llamada le ayuda a solucionar problemas de conexión o llamada con Skype Empresarial. Análisis de llamada muestra información detallada sobre los dispositivos, redes y conectividad de las llamadas y reuniones de cada usuario en su cuenta de Skype Empresarial. Si crea, del sitio y de inquilinos se ha agregado información para el análisis de llamadas, también se mostrarán para cada llamada y sesión. Información disponible a través de análisis de llamadas le permite averiguar por qué un usuario tenía una llamada de una mala o experiencia de reunión.
  
> [!NOTE]
> Análisis de llamada está en vista previa. Texto e imágenes que se describen aquí no pueden coincidir con su experiencia. 
  
## Solucionar problemas de calidad de llamada mediante el análisis de llamadas

El nivel de permisos que se le asignado determina qué tipo de información que tiene acceso en el análisis de llamadas:
  
- **Skype para el Administrador de empresa**: tiene acceso a toda la información de análisis de llamadas y en el centro de administración de Skype Empresarial.
    
- **Agente de servicio de asistencia con permisos de nivel 1**: vea un conjunto de datos en el análisis de llamar limitado. Puede solucionar llamadas, pero deberá entregar problemas con las reuniones con un agente de nivel 2. No tiene acceso al resto del centro de administración de Skype Empresarial.
    
- **Agente de servicio de asistencia con permisos de nivel 2**: ver todos los datos disponibles en el análisis de llamada y puede ayudar a solucionar problemas relacionados con llamadas y reuniones. No tiene acceso al resto del centro de administración de Skype Empresarial.
    
Si necesita ayuda con los permisos, vea el Administrador de Skype Empresarial.
  
 **Abra el análisis de llamar como agente de un departamento de soporte técnico de nivel 1 o nivel 2**
  
1. Vaya a [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com)y, a continuación, inicie sesión con su nombre de usuario y contraseña.
    
2. En **Búsqueda de usuarios**, comience a escribir el nombre o el sip dirección del usuario cuyas desea solucionar problemas y, a continuación, seleccione el usuario de la lista de llamadas.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. En el **historial de llamadas**, seleccione la llamada o reunión que desee solucionar problemas.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Seleccione la ficha **Opciones avanzadas** y, a continuación, busque elementos amarillos y rojos que indican la llamada de una mala calidad o problemas de conexión.
    
    En los detalles de la sesión de cada llamada o reunión, problemas poco importantes aparecen en amarillo. (Por ejemplo, en la siguiente captura de pantalla, los valores son en amarillo para vibración promedio, vibración Max y velocidad de pérdida de paquetes promedio.) Si algo es amarillo, está fuera de rango normal y puede contribuir al problema, pero es probable que la causa principal del problema. Si algo es rojo, es un problema importante, y es probable que la causa principal de la calidad de llamada deficiente para esta sesión.
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
En algunas ocasiones, la calidad de la experiencia de datos no se recibió para sesiones de audio. A menudo esto se debe a la llamada y colocar conexión con el cliente de terminación. Cuando ocurre esto, la clasificación de sesión es "no disponible".
  
Para las sesiones de audio que tengan la calidad de los datos de la experiencia (QoE), la siguiente tabla describe los problemas principales que calificar una sesión como "mala".
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Configuración de la llamada  <br/> |Sesión  <br/> |El código de error Ms-diag 20-29 indica error en la configuración de la llamada. El usuario no pudo unirse a la llamada o reunión.  <br/> |
|Red audio clasifica llamada deficiente  <br/> |Sesión  <br/> |Problemas de calidad de red encontrados en áreas como la pérdida de paquetes, vibración, degradación NMOS, RTT, u oculten relación. Para obtener más información acerca de las condiciones que se utiliza para clasificar una mala llamadas, consulte esta [entrada de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no funciona correctamente. Dispositivo no funciona razones es: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Configurar Skype para Business Analytics de llamadas](set-up-skype-for-business-call-analytics.md)

