---
title: 'Lync Server 2013: Crear el diseño de la topología inicial'
TOCTitle: Crear el diseño inicial
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615047(v=OCS.15)
ms:contentKeyID: 52061972
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear el diseño de la topología inicial para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Tras haber finalizado la instalación de Lync Server 2013, herramienta de planeación, ya puede iniciar la Herramienta de planeación y comenzar el diseño de la infraestructura propuesta de Lync Server 2013.


> [!NOTE]
> La Herramienta de planeación es una herramienta que funciona con asistentes para informar detalladamente al usuario sobre el proceso de toma de decisiones para diseñar los sitios y la topología. La finalidad de este tema no es proporcionar una introducción general exhaustiva, sino simplemente permitir que le sea más fácil usar la Herramienta de planeación en las sesiones de diseño.



## Para empezar a usar la Herramienta de planeación y crear el diseño inicial

1.  Inicie Lync Server 2013, Herramienta de planeación: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Herramienta de planeación**.

2.  Tras iniciar la Herramienta de planeación, en pantalla aparece la página **Herramienta de planeación de Microsoft Lync Server 2013**. Para empezar el diseño, elija una de las opciones siguientes:
    
      - **Opción 1: Introducción**   Si se hace clic en **Introducción**, aparecen una serie de preguntas de tipo entrevista con las correspondientes opciones de selección para definir los criterios. Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio. Para completar esta opción, vaya al paso 3.
    
      - **Opción 2: Diseñar sitios**   Si se hace clic en **Diseñar sitios** en la página inicial, se omiten las preguntas de tipo entrevista que aparecen en la sección **Introducción**. Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción. Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**. Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.
    
      - **Opción 3: Mostrar la topología guardada**   Si ya ha completado y guardado una topología por haber usado anteriormente la Herramienta de planeación, puede prescindir de casi todos estos pasos, abrir la topología y verla en pantalla. Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio. Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.

3.  Haga clic en **Introducción** para comenzar el diseño de la topología de Lync Server 2013.

4.  Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.
    
    > [!TIP]  
    > Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad. Si necesita más datos, haga clic en <strong>Más información</strong> para leer información detallada en la documentación sobre el planeamiento de Lync Server 2013 en el sitio web de Microsoft TechNet. Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.
    


5.  Seleccione las opciones pertinentes para el diseño. Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.

6.  Haga clic en **Diseñar sitios** para definir el sitio central.
    

    > [!NOTE]
    > Cada topología de Lync Server 2013 debe tener como mínimo un sitio central. El diseño puede constar de un solo sitio central, un sitio central con varios sitios de sucursal, varios sitios centrales o bien una serie de sitios centrales con sitios de sucursal asociados con cada sitio central.



7.  En **Nombre del sitio**, escriba el nombre con el que se identificará este sitio central.

8.  En **Usuarios alojados en el sitio**, escriba la cantidad prevista de usuarios locales que se ubicarán en este sitio central.

9.  En **Usuarios alojados en la nube**, escriba la cantidad prevista de usuarios simultáneos en línea que se hospedarán en este sitio central.

10. Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.
    
    > [!IMPORTANT]  
    > En esta fase del diseño, solamente puede activar o desactivar opciones de implementación. Ahora bien, en una fase posterior de la Herramienta de planeación podrá configurar más opciones. También hay opciones no disponibles y que no se pueden desactivar. Además, es posible que deba desactivar una opción para poder desactivar otra. Por ejemplo, si desactiva la opción <strong>Telefonía IP empresarial</strong> debajo de Voz, las opciones <strong>Grupo de respuesta</strong>, <strong>Anuncio</strong> y <strong>Estacionamiento de llamadas</strong> debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.
    


11. Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.

12. Las páginas siguientes solicitan información sobre dominios SIP, configuración de conferencias, configuraciones de voz e infraestructura, Mensajería unificada de Exchange, acceso de usuarios externos, configuración de Chat persistente, configuración de cliente, opciones de colocación y sitios de sucursal. Responda a estas preguntas según considere adecuado.

13. La última pregunta es si se desea crear otro sitio central. Si selecciona **Sí**, la Herramienta de planeación vuelve a la página Sitios centrales. Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.

14. Para ver una topología que ya existe, haga clic en **Mostrar**.

15. Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.

16. La Herramienta de planeación muestra la página Topología global. Ahora, la topología puede empezar a editarse, actualizarse o cambiarse con las herramientas disponibles en la Herramienta de planeación.

## Vea también

#### Conceptos

[Edición del diseño en Lync Server 2013](lync-server-2013-editing-the-design.md)

