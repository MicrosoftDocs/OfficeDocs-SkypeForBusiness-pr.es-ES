---
title: Combinar mediante el Asistente para combinaciones de Topology Builder
TOCTitle: Combinar mediante el Asistente para combinaciones de Topology Builder
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48276589
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Combinar mediante el Asistente para combinaciones de Topology Builder

 

_**Última modificación del tema:** 2012-10-02_

1.  Descargue la implementación actual con el Generador de topologías.

2.  En el menú **Acción** , seleccione **Combinar Office Communications Server 2007 R2** .

3.  Después, haga clic en **Siguiente** .

4.  En **Especificar configuración perimetral** , haga clic en **Agregar** .
    
    ![Asistente de topología de combinación, página Especificar configuración perimetral](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Asistente de topología de combinación, página Especificar configuración perimetral")  

5.  En **Especificar tipo de servidor perimetral** , escriba el tipo de configuración del servidor perimetral y haga clic en **Siguiente** . En este ejemplo, se usa la opción **Servidor perimetral único** .
    
    > [!IMPORTANT]  
    > No se admite la configuración de <strong>servidor perimetral expandido</strong> . Un <strong>servidor perimetral expandido</strong> debe convertirse primero en <strong>servidor perimetral único</strong> o en <strong>servidor perimetral consolidado con equilibrio de carga</strong> .
    


6.  En **Especificar configuración perimetral interna** , escriba la información relevante del FQDN y los puertos internos del grupo de servidores perimetrales según sea necesario y haga clic en **Siguiente** .
    
    ![Cuadro de diálogo Especificar configuración perimetral interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Cuadro de diálogo Especificar configuración perimetral interna")  

7.  En **Especificar perímetro externo** , escriba la información del FQDN de conferencia web del servidor perimetral.
    
    > [!IMPORTANT]  
    > Antes de hacer clic en <strong>Siguiente</strong> , realice el próximo paso de este procedimiento. Es muy importante que no omita este paso.
    


8.  Active la casilla **Este grupo de servidores perimetrales se usa para federación y conectividad de mensajería instantánea pública** si tiene previsto usar el servidor perimetral de Office Communications Server 2007 R2 para la federación. Si tiene varios servidores perimetrales implementados, solamente uno de ellos estará habilitado para la federación. Si no activa esta casilla y decide más adelante que desea habilitar la federación, deberá ejecutar de nuevo el asistente para combinar del Generador de topologías y volver a publicar la topología.
    
    ![Cuadro de diálogo Servidor perimetral, página Especificar perímetro externo](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Cuadro de diálogo Servidor perimetral, página Especificar perímetro externo")  

9.  En **Especificar próximo salto** , escriba el nombre de dominio completo de la ubicación del próximo salto en el entorno. Haga clic en **Finalizar** .
    
    ![Cuadro de diálogo Servidor perimetral, página Especificar próximo salto](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Cuadro de diálogo Servidor perimetral, página Especificar próximo salto")  

10. En **Especificar configuración perimetral** , si se agregaron todos los servidores perimetrales de Office Communications Server 2007 R2, haga clic en **Siguiente** . Si tiene más servidores perimetrales de Office Communications Server 2007 R2 para agregar, repita este procedimiento desde el paso 4.

11. En **Especificar puerto SIP interno** , seleccione la configuración predeterminada (es decir, si no modificó el puerto SIP predeterminado). Cambie esta opción como sea necesario si no usa el puerto predeterminado 5061 y haga clic en **Siguiente** .

12. En **Resumen** , haga clic en **Siguiente** para comenzar a combinar topologías.

13. La página del asistente comprueba que la combinación de topologías se ha realizado correctamente.

14. En la columna **Estado** , verifique que el valor es **Correcto** y haga clic en **Finalizar** .

15. En el panel izquierdo del Generador de topologías, debe aparecer ahora **BackCompatSite** , que indica que el entorno de Office Communications Server 2007 R2 se ha combinado con Lync Server 2013.
    
    ![Generador de topologías con una topología combinada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generador de topologías con una topología combinada")  

16. En el menú **Acción** , haga clic en **Publicar topología** y en **Siguiente** .

17. Cuando el **asistente para publicación** haya finalizado, haga clic en **Finalizar** .
    

    > [!NOTE]
    > Es importante que complete el siguiente tema, <A href="import-policies-and-settings.md">Importar directivas y configuraciones</A>, para garantizar que la configuración de directivas heredada se importa correctamente en Lync Server 2013.


