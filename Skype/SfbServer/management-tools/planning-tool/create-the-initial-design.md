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
description: Cuando haya terminado de instalar el Skype para la herramienta de planeación de Business Server, está listo para iniciar la herramienta de planeación y empezar a diseñar la propuesta Skype para infraestructura de Business Server 2015.
ms.openlocfilehash: 73fd6f4a83ec5aec6808124728c1c73419bcdd28
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246669"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Crear el diseño de la topología inicial para Skype Empresarial Server 2015

Cuando haya terminado de instalar el Skype para la herramienta de planeación de Business Server, está listo para iniciar la herramienta de planeación y empezar a diseñar la propuesta Skype para infraestructura de Business Server 2015.

> [!NOTE]
>  La herramienta de planeación es una herramienta basada en Asistente con guías detalladas para informar a su proceso de toma de decisiones en el diseño de los sitios y la topología. En este tema está pensado no como una guía exhaustiva, pero simplemente para ayudar a Introducción al uso de la herramienta de planeación en las sesiones de diseño.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a usar la herramienta de planeación y crear el diseño inicial

1. Iniciar el Skype para la herramienta de planeación de Business Server 2015: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Herramienta de planeación**.

2. Después de que ha iniciado la herramienta de planeación, aparece la página de **bienvenida a la herramienta de planeación de Skype para Business Server 2015** . Para empezar el diseño, elija una de las opciones siguientes:

   - **Opción 1: Introducción a** Al hacer clic en **Empezar a** proporciona una serie de preguntas de la entrevista con selecciones relevantes para definir los criterios específica. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.

   - **Opción 2: diseño de sitios de** Al hacer clic en **Diseñar sitios** en la página de bienvenida omite las preguntas de entrevista presentadas en la sección de **Introducción** . Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción. Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.

   - **Opción 3: mostrar la topología guardada** Si ya ha completado y ha guardado una topología mediante el uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos e iniciar abriendo y mostrar la topología. Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3. Haga clic en **Introducción** para comenzar a diseñar su Skype para topología empresarial Server 2015.

4. Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.

    > [!TIP]
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad. Si necesita obtener más información, haga clic en **más información** para leer información detallada de la Skype para la documentación de planeación de Business Server 2015 en el sitio Web de Microsoft. Debe tener la conectividad a Internet para acceder al sitio Web de Microsoft.

5. Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6. Haga clic en **Diseñar sitios** para definir el sitio central.

    > [!NOTE]
    > Cada Skype para Business Server 2015 topología tendrá al menos un sitio central. El diseño de la que tenga un único sitio central, un sitio central con un número de sitios de sucursal, un número de sitios centrales o un número de sitios centrales con sitios de sucursal asociados con cada sitio central.

7. En **Nombre del sitio**, escriba el nombre que identificará este sitio central.

8. En **Los usuarios hospedados del sitio**, escriba el número esperado de usuarios simultáneos de local que se ubicarán en este sitio central.

9. En **Los usuarios hospedados de nube**, escriba el número esperado de usuarios simultáneos en línea que se ubicarán en este sitio central.

10. Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.

    > [!IMPORTANT]
    > En esta fase del diseño, solamente puede activar o desactivar opciones de implementación. Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planeación. También hay opciones no disponibles y que no se pueden desactivar. Además, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción **Telefonía IP empresarial** debajo de Voz, las opciones **Grupo de respuesta**, **Anuncio** y **Estacionamiento de llamadas** debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.

11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Formular las páginas siguientes para obtener información acerca de SIP dominios, configuración de la conferencia, configuración de voz e infraestructura, mensajería unificada de Exchange, el acceso de usuarios externos, Chat persistente configuración, configuración del cliente, las opciones de colocación y sitios de sucursal. Responda a estas preguntas según considere adecuado.

13. La pregunta final se pregunta si desea crear otro sitio central. Si selecciona **Sí**, la herramienta de planeación se devuelve a la página sitios centrales. Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.

14. Para ver una topología que ya existe, haga clic en **Mostrar**.

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La herramienta de planeación muestra la página topología Global. Ahora puede empezar a editar, actualizar o cambiar la topología mediante el uso de las herramientas disponibles en la herramienta de planeación.

## <a name="see-also"></a>Vea también

[Edición del diseño](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)