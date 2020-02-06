---
title: Crear el diseño de la topología inicial para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Cuando haya terminado de instalar la herramienta de planeación de Skype empresarial, estará listo para iniciar la herramienta de planificación y empezar a diseñar la infraestructura de Skype empresarial Server 2015.
ms.openlocfilehash: 8c19551d2273b992b5148646e28d726f5aea5900
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816499"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Crear el diseño de la topología inicial para Skype Empresarial Server 2015

Cuando haya terminado de instalar la herramienta de planeación de Skype empresarial, estará listo para iniciar la herramienta de planificación y empezar a diseñar la infraestructura de Skype empresarial Server 2015.

> [!NOTE]
>  La herramienta de planeación es una herramienta guiada por un asistente con guías detalladas para informar sobre el proceso de toma de decisiones en el diseño de sitios y topología. Este tema está pensado no es una guía exhaustiva, pero simplemente para ayudarle a empezar a usar la herramienta de planificación en sus sesiones de diseño.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a usar la herramienta de planificación y crear el diseño inicial

1. Inicie la herramienta de planeación de Skype empresarial Server 2015: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server 2015**y, a continuación, haga clic en **herramienta de planificación**.

2. Después de iniciar la herramienta de planeación, aparece la página de **bienvenida a la herramienta de planeación de Skype empresarial Server 2015** . Para empezar el diseño, elija una de las opciones siguientes:

   - **Opción 1: Introducción** Haga clic en **comenzar** proporciona una serie específica de preguntas de la entrevista con las selecciones pertinentes para definir los criterios. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.

   - **Opción 2: diseñar sitios** Al hacer clic en **diseñar sitios** en la página de bienvenida, se omiten las preguntas de entrevistas presentadas en **la sección introducción** . Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción. Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.

   - **Opción 3: Mostrar la topología guardada** Si ya ha completado y guardado una topología a través del uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos y empezar abriendo y mostrando la topología. Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3. Haga **clic en introducción para** empezar a diseñar su topología de 2015 de Skype empresarial Server.

4. Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.

    > [!TIP]
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad. Si necesita más información, haga clic en **más** información para leer la información detallada de la documentación de planificación de Skype empresarial Server 2015 en el sitio web de Microsoft. Para tener acceso al sitio web de Microsoft, debe tener conexión a Internet.

5. Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6. Haga clic en **diseñar sitios** para definir el sitio central.

    > [!NOTE]
    > Cada topología de Skype empresarial Server 2015 tendrá al menos un sitio central. Su diseño puede tener un único sitio central, un sitio central con un número de sitios de sucursales, una serie de sitios centrales o varios sitios centrales con sitios de sucursales asociados con cada sitio central.

7. En **nombre del sitio**, escriba el nombre que identificará a este sitio central.

8. En **usuarios alojados del sitio**, escriba el número esperado de usuarios simultáneos locales que estarán alojados en este sitio central.

9. En **usuarios domésticos en la nube**, escriba el número esperado de usuarios simultáneos en línea que estarán alojados en este sitio central.

10. Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.

    > [!IMPORTANT]
    > En esta fase del diseño, solamente puede activar o desactivar opciones de implementación. Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planificación. También hay opciones no disponibles y que no se pueden desactivar. Además, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción **Telefonía IP empresarial** debajo de Voz, las opciones **Grupo de respuesta**, **Anuncio** y **Estacionamiento de llamadas** debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.

11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Las siguientes páginas solicitan información sobre los dominios SIP, la configuración de la Conferencia, la configuración de voz y la infraestructura, la mensajería unificada de Exchange, el acceso de usuarios externos, la configuración de chat persistente, la configuración de cliente, las opciones de collocation y los sitios de sucursales Responda a estas preguntas según considere adecuado.

13. La pregunta final pregunta si desea crear otro sitio central. Si selecciona **sí**, la herramienta de planeación vuelve a la página sitios centrales. Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.

14. Para ver una topología que ya existe, haga clic en **Mostrar**.

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La herramienta de planeación muestra la página de topología global. Ahora puede empezar a editar, actualizar o cambiar la topología mediante las herramientas disponibles en la herramienta de planificación.

## <a name="see-also"></a>Vea también

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
