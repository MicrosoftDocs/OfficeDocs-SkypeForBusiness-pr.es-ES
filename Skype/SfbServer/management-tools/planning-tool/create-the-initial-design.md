---
title: Crear el diseño de la topología inicial para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Una vez que haya terminado de instalar el Skype para la herramienta de planeación de Business Server, está listo para iniciar la herramienta de planeación y empezar a diseñar la propuesta Skype para la infraestructura de servidor de negocios 2015.
ms.openlocfilehash: 9925ad9e4294ef2a1e4b90f6e1de9780bbb83260
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Crear el diseño de la topología inicial para Skype Empresarial Server 2015
 
Una vez que haya terminado de instalar el Skype para la herramienta de planeación de Business Server, está listo para iniciar la herramienta de planeación y empezar a diseñar la propuesta Skype para la infraestructura de servidor de negocios 2015.
  
> [!NOTE]
>  La herramienta de planeación es una herramienta basada en Asistente con guías detalladas para informar a su proceso de toma de decisiones en el diseño de sus sitios y topología. Este tema está pensado no como una guía exhaustiva, sino simplemente le ayuda a comenzar con la herramienta de planificación de las sesiones de diseño.
  
### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a utilizar la herramienta de planeación y crear el diseño inicial

1. Iniciar el Skype para la herramienta de planeación de 2015 Business Server: haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Herramienta de planeación**.
    
2. Después de que ha iniciado la herramienta de planeación, aparece la página de **bienvenida de la herramienta de planeación de Skype para Business Server 2015** . Para empezar el diseño, elija una de las opciones siguientes:
    
   - **Opción 1: comenzar** Haga clic en **Comenzar** proporciona una serie de preguntas de la entrevista con selecciones pertinentes para definir los criterios específica. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.
    
   - **Opción 2: diseñar sitios** Haga clic en **Sitios de diseño** en la página de bienvenida omite las preguntas de la entrevista presentadas en la sección **Introducción** . Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción. Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.
    
   - **Opción 3: mostrar la topología guardada** Si ya ha completado y ha guardado una topología mediante el uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos e iniciar abriendo y mostrar la topología. Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.
    
3. Haga clic en **Empezar** para comenzar a diseñar su Skype para Business Server 2015 topología.
    
4. Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.
    
    > [!TIP]
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad. Si necesita información adicional, haga clic en **más información** para leer información detallada de la Skype para Business Server Planning 2015 documentación en el sitio Web de Microsoft TechNet. Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.
  
5. Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características. 
    
6. Haga clic en **Diseñar sitios** para definir el sitio central.
    
    > [!NOTE]
    > Cada Skype para Business Server 2015 topología tendrá al menos un sitio central. El diseño puede tener un único sitio central, un sitio central con un número de sucursales, un número de sitios centrales o un número de sitios centrales con sucursales asociados con cada sitio central. 
  
7. En **Nombre del sitio**, escriba el nombre que identifique este sitio central.
    
8. En **Usuarios de alojamiento de sitios**, escriba el número esperado de usuarios simultáneos de locales que se alojará en este sitio central.
    
9. En la **Nube alojados usuarios**, escriba el número esperado de usuarios simultáneos en línea que se alojará en este sitio central.
    
10. Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.
    
    > [!IMPORTANT]
    > En esta fase del diseño, solamente puede activar o desactivar opciones de implementación. Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planeación. También hay opciones no disponibles y que no se pueden desactivar. Además, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción **Telefonía IP empresarial** debajo de Voz, las opciones **Grupo de respuesta**, **Anuncio** y **Estacionamiento de llamadas** debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.
  
11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.
    
12. Las siguientes páginas de pedirán información sobre SIP dominios, configuración de la conferencia, configuración de voz e infraestructura, mensajería unificada de Exchange, acceso de usuarios externos, Chat persistente configuración, configuración de cliente, opciones de colocación y sucursales. Responda a estas preguntas según considere adecuado.
    
13. La pregunta final que le preguntará si desea crear otro sitio central. Si selecciona **Sí**, la herramienta de planeación se devuelve a la página de sitios centrales. Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.
    
14. Para ver una topología que ya existe, haga clic en **Mostrar**.
    
15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.
    
16. La herramienta de planeación muestra la página de la topología Global. Ahora puede empezar a editar, actualizar o cambiar la topología utilizando las herramientas disponibles en la herramienta de planeación.
    
## <a name="see-also"></a>Vea también

#### 

[Edición del diseño](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

