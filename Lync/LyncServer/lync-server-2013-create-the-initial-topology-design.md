---
title: 'Lync Server 2013: crear el diseño de la topología inicial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Crear el diseño de topología inicial para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una vez que haya finalizado la instalación de la herramienta de planeación de Lync Server 2013, estará listo para iniciar la herramienta de planeación y comenzar a diseñar la infraestructura de Lync Server 2013 propuesta.

<div>


> [!NOTE]  
> La herramienta de planeación es una herramienta guiada por asistente con guías detalladas para informar sobre el proceso de toma de decisiones en el diseño de los sitios y la topología. Este tema no está pensado como guía exhaustiva, pero simplemente para ayudarle a empezar a usar la herramienta de planeación en sus sesiones de diseño.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a usar la Herramienta de planeación y crear el diseño inicial

1.  Inicie la herramienta de planeación de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **herramienta de planeación**.

2.  Una vez iniciada la herramienta de planeación, aparece la página **de bienvenida de la herramienta de planeación de Microsoft Lync Server 2013** . Elija una de las siguientes opciones para comenzar el diseño:
    
      - **Opción 1:**   Introducción **al hacer clic en Introducción proporciona** una serie específica de preguntas de la entrevista con las selecciones pertinentes para definir los criterios. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.
    
      - **Opción 2: diseñar sitios**   al hacer clic en **diseñar sitios** en la página de bienvenida se omiten las preguntas **de la entrevista** que se presentan en la sección introducción. La información que se habría recopilado al responder a las preguntas de la entrevista en **la sección introducción se establece en valores** predeterminados con esta opción. Al hacer clic en **diseñar sitios**, el diseñador experimentado puede omitir la entrevista inicial y cambiar los valores predeterminados, según sea necesario, en la página de inicio de los **sitios centrales** . Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.
    
      - **Opción 3: Mostrar la topología**   guardada si ya ha completado y guardado una topología a través del uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos y empezar por abrir y mostrar la topología. También puede realizar cambios y actualizaciones en la topología, reguardarla y, a continuación, exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3.  Haga **clic en introducción para** empezar a diseñar su topología de Lync Server 2013.

4.  Responda a cada pregunta seleccionado el criterio correcto para el diseño; a continuación, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **atrás** para realizar cambios en las páginas anteriores.
    
    <div>
    

    > [!TIP]  
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en prácticas preferidas y la planeación de la capacidad. Si necesita más información, haga clic en <STRONG>más</STRONG> información para leer información detallada de la documentación de planeación de Lync Server 2013 en el sitio web de Microsoft TechNet. Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.

    
    </div>

5.  Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6.  Haga clic en **diseñar sitios** para definir el sitio central.
    
    <div>
    

    > [!NOTE]  
    > Cada topología de Lync Server 2013 tendrá al menos un sitio central. El diseño puede tener un único sitio central, un sitio central con varios sitios de sucursal, una serie de sitios centrales o una serie de sitios centrales con sitios de sucursal asociados con cada sitio central.

    
    </div>

7.  En **nombre del sitio**, escriba el nombre que va a identificar este sitio central.

8.  En **usuarios alojados**en el sitio, escriba el número previsto de usuarios simultáneos locales que se hospedarán en este sitio central.

9.  En **usuarios alojados en la nube**, escriba el número previsto de usuarios simultáneos en línea que se hospedarán en este sitio central.

10. Modifique las selecciones para colaboración en línea, usuarios, voz, opciones de implementación adicionales o aplicaciones de servidor, según sea necesario.
    
    <div>
    

    > [!IMPORTANT]  
    > En este punto del diseño, solo puede activar o desactivar las opciones de la implementación. Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planeación. También hay opciones no disponibles y que no se pueden desactivar. Asimismo, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción <STRONG>telefonía IP empresarial</STRONG> en voz, las opciones <STRONG>grupo de respuesta</STRONG>, <STRONG>anuncio</STRONG>y <STRONG>estacionamiento de llamadas</STRONG> en aplicaciones de servidor (todas ellas son características de Enterprise Voice) también se desactivan.

    
    </div>

11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Las páginas siguientes solicitan información sobre los dominios SIP, la configuración de conferencia, la configuración de voz y la infraestructura, la mensajería unificada de Exchange, el acceso de usuarios externos, la configuración de chat persistente, la configuración de cliente, las opciones de combinación y los sitios de sucursal. Responda a estas preguntas.

13. La pregunta final pregunta si desea crear otro sitio central. Si selecciona **sí**, la herramienta de planeación vuelve a la página sitios centrales. Si selecciona **no**, haga clic en **siguiente**y, a continuación, haga clic en **dibujo** para mostrar la vista de topología global de alto nivel.

14. Para ver una topología existente, haga clic en **Mostrar**.

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La herramienta de planeación muestra la página topología global. Ahora puede empezar a editar, actualizar o cambiar la topología con las herramientas disponibles en la herramienta de planeación.

</div>

<div>

## <a name="see-also"></a>Vea también


[Edición del diseño en Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

