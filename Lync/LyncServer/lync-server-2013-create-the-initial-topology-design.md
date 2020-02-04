---
title: 'Lync Server 2013: crear el diseño de topología inicial'
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
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Crear el diseño de topología inicial para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una vez que haya terminado de instalar Lync Server 2013, la herramienta de planeación, estará listo para iniciar la herramienta de planeación y empezar a diseñar la infraestructura de Lync Server 2013 propuesta.

<div>


> [!NOTE]  
> La herramienta de planeación es una herramienta guiada por un asistente con guías detalladas para informar sobre el proceso de toma de decisiones en el diseño de sitios y topología. Este tema está pensado no es una guía exhaustiva, pero simplemente para ayudarle a empezar a usar la herramienta de planificación en sus sesiones de diseño.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para empezar a usar la herramienta de planificación y crear el diseño inicial

1.  Inicie Lync Server 2013, herramienta de planeación: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **herramienta de planeación**.

2.  Después de iniciar la herramienta de planeación, aparece la página **de bienvenida a la herramienta de planeación de Microsoft Lync Server 2013** . Para empezar el diseño, elija una de las opciones siguientes:
    
      - **Opción 1:**   Introducción al hacer clic en **comenzar** proporciona una serie de preguntas de entrevista con las selecciones pertinentes para definir los criterios. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.
    
      - **Opción 2: diseñar sitios**   al hacer clic en **sitios de diseño** , en la página de bienvenida se omiten las preguntas de entrevista que se presentan en **la sección introducción** . Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción. Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.
    
      - **Opción 3: Mostrar la topología**   guardada si ya ha completado y guardado una topología a través del uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos y empezar abriendo y mostrando la topología. Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3.  Haga **clic en introducción para** empezar a diseñar su topología de 2013 de Lync Server.

4.  Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.
    
    <div>
    

    > [!TIP]  
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad. Si necesita más información, haga clic en <STRONG>más</STRONG> información para obtener información detallada de la documentación de planeación de Lync Server 2013 en el sitio web de Microsoft TechNet. Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.

    
    </div>

5.  Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6.  Haga clic en **diseñar sitios** para definir el sitio central.
    
    <div>
    

    > [!NOTE]  
    > Cada topología de Lync Server 2013 tendrá al menos un sitio central. Su diseño puede tener un único sitio central, un sitio central con un número de sitios de sucursales, una serie de sitios centrales o varios sitios centrales con sitios de sucursales asociados con cada sitio central.

    
    </div>

7.  En **nombre del sitio**, escriba el nombre que identificará a este sitio central.

8.  En **usuarios alojados del sitio**, escriba el número esperado de usuarios simultáneos locales que estarán alojados en este sitio central.

9.  En **usuarios domésticos en la nube**, escriba el número esperado de usuarios simultáneos en línea que estarán alojados en este sitio central.

10. Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.
    
    <div>
    

    > [!IMPORTANT]  
    > En esta fase del diseño, solamente puede activar o desactivar opciones de implementación. Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planificación. También hay opciones no disponibles y que no se pueden desactivar. Además, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción <STRONG>Telefonía IP empresarial</STRONG> debajo de Voz, las opciones <STRONG>Grupo de respuesta</STRONG>, <STRONG>Anuncio</STRONG> y <STRONG>Estacionamiento de llamadas</STRONG> debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.

    
    </div>

11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Las siguientes páginas solicitan información sobre los dominios SIP, la configuración de la Conferencia, la configuración de voz y la infraestructura, la mensajería unificada de Exchange, el acceso de usuarios externos, la configuración de chat persistente, la configuración de cliente, las opciones de collocation y los sitios de sucursales Responda a estas preguntas según considere adecuado.

13. La pregunta final pregunta si desea crear otro sitio central. Si selecciona **sí**, la herramienta de planeación vuelve a la página sitios centrales. Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.

14. Para ver una topología que ya existe, haga clic en **Mostrar**.

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La herramienta de planeación muestra la página de topología global. Ahora puede empezar a editar, actualizar o cambiar la topología mediante las herramientas disponibles en la herramienta de planificación.

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

