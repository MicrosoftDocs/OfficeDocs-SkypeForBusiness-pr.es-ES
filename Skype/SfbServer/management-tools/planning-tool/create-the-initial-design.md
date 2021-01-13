---
title: Crear el diseño de topología inicial para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Cuando haya terminado de instalar la Herramienta de planeación de Skype Empresarial Server, estará listo para iniciar la Herramienta de planeación y empezar a diseñar la infraestructura propuesta de Skype Empresarial Server 2015.
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834970"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Crear el diseño de topología inicial para Skype Empresarial Server 2015

Cuando haya terminado de instalar la Herramienta de planeación de Skype Empresarial Server, estará listo para iniciar la Herramienta de planeación y empezar a diseñar la infraestructura propuesta de Skype Empresarial Server 2015.

> [!NOTE]
>  La Herramienta de planeación es una herramienta controlada por asistentes con guías detalladas para informar al proceso de toma de decisiones en el diseño de los sitios y la topología. Este tema no es una guía exhaustiva, sino simplemente para ayudarle a empezar a usar la Herramienta de planeación en las sesiones de diseño.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a usar la Herramienta de planeación y crear el diseño inicial

1. Inicie la Herramienta de planeación de Skype Empresarial Server 2015: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Herramienta de **planeación.**

2. Una vez iniciada la Herramienta de planeación, aparece la página De bienvenida de la Herramienta de planeación para **Skype Empresarial Server 2015.** Elija una de las siguientes opciones para comenzar el diseño:

   - **Opción 1: Introducción** Al **hacer clic en Introducción** se proporciona una serie específica de preguntas de entrevista con selecciones relevantes para definir los criterios. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.

   - **Opción 2: Diseñar sitios** Al **hacer clic en Diseñar** sitios en la página principal, se omiten las preguntas de entrevista presentadas en la **sección** Introducción. La información que se habría recopilado respondiendo  a las preguntas de la entrevista de la sección Introducción se establece en los valores predeterminados con esta opción. Al hacer **clic en Diseñar sitios,** el diseñador experimentado puede omitir la entrevista inicial y cambiar los valores predeterminados, según sea necesario, en la página de inicio **de Sitios** centrales. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.

   - **Opción 3: Mostrar la topología guardada** Si ya ha completado y guardado una topología mediante el uso anterior de la Herramienta de planeación, puede omitir la mayoría de estos pasos y empezar abriendo y mostrando la topología. También puede realizar cambios y actualizaciones en la topología, volver a guardarla y, a continuación, exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3. Haga **clic en Introducción** para empezar a diseñar la topología de Skype Empresarial Server 2015.

4. Responda a cada pregunta seleccionado el criterio correcto para el diseño; a continuación, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga **clic en** Atrás para realizar cambios en páginas anteriores.

    > [!TIP]
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en prácticas preferidas y la planeación de la capacidad. Si necesita más información, haga clic en Más información para leer información detallada de la documentación de planeación de Skype Empresarial Server 2015 en el sitio web de Microsoft.  Debe tener conectividad a Internet para acceder al sitio web de Microsoft.

5. Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6. Haga **clic en Diseñar sitios** para definir el sitio central.

    > [!NOTE]
    > Cada topología de Skype Empresarial Server 2015 tendrá al menos un sitio central. El diseño puede tener un único sitio central, un sitio central con varios sitios de sucursal, varios sitios centrales o varios sitios centrales con sitios de sucursal asociados a cada sitio central.

7. En **Nombre del sitio,** escriba el nombre que identificará este sitio central.

8. En **Usuarios del sitio principal,** escriba el número esperado de usuarios simultáneos locales que se van a albergar en este sitio central.

9. En **Usuarios en la nube,** escriba el número esperado de usuarios simultáneos en línea que se van a albergar en este sitio central.

10. Modifique las selecciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor, según sea necesario.

    > [!IMPORTANT]
    > En este punto del diseño, solo puede seleccionar o borrar opciones para la implementación. Sin embargo, puede configurar más opciones en una fase posterior de la Herramienta de planeación. También hay opciones no disponibles y que no se pueden desactivar. Asimismo, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción **Telefonía IP empresarial** en Voz, también  se borrarán las opciones Grupo de **respuesta,** Anuncio y Estacionamiento de llamadas en Aplicaciones de servidor (todas las cuales son características de Telefonía IP empresarial).

11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Las páginas siguientes solicitan información sobre dominios SIP, configuración de conferencia, configuración de voz e infraestructura, mensajería unificada de Exchange, acceso de usuarios externos, configuración de chat persistente, configuración de cliente, opciones de colocación y sitios de sucursal. Responda a estas preguntas.

13. La pregunta final se hace si desea crear otro sitio central. Si selecciona **Sí,** la Herramienta de planeación volverá a la página Sitios centrales. Si selecciona **No,** haga clic en **Siguiente** y, a continuación, haga clic en **Dibujar** para mostrar la vista Topología global de alto nivel.

14. Para ver una topología existente, haga clic en **Mostrar.**

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La Herramienta de planeación muestra la página Topología global. Ahora puede empezar a editar, actualizar o cambiar la topología mediante las herramientas disponibles en la Herramienta de planeación.

## <a name="see-also"></a>Ver también

[Edición del diseño](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
