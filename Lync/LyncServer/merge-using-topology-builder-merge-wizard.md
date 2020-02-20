---
title: Combinar mediante el Asistente de combinación del generador de topologías
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8578217d5e3b35351937dbf2838e2994e74fb32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Combinar mediante el Asistente de combinación del generador de topologías

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

1.  Descargue la implementación actual con el Generador de topologías.

2.  En el menú **Acción**, seleccione **Combinar Office Communications Server 2007 R2**.

3.  Haga clic en **Siguiente**.

4.  En **Especificar configuración perimetral**, haga clic en **Agregar**.
    
    ![Asistente para combinar topología, especificar página de configuración perimetral](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración perimetral")  

5.  En **Especificar tipo de servidor perimetral**, escriba el tipo de configuración del servidor perimetral y haga clic en **Siguiente**. En este ejemplo, se usa la opción **Servidor perimetral único**.
    
    <div>
    

    > [!IMPORTANT]  
    > No se admite la configuración de <STRONG>servidor perimetral expandido</STRONG>. Un <STRONG>servidor perimetral expandido</STRONG> debe convertirse primero en <STRONG>servidor perimetral único</STRONG> o en <STRONG>servidor perimetral consolidado con equilibrio de carga</STRONG>.

    
    </div>

6.  En **especificar configuración perimetral interna** , escriba la información relevante del FQDN y los puertos internos del grupo de servidores perimetrales según sea necesario y, a continuación, haga clic en **siguiente**.
    
    ![Cuadro de diálogo especificar configuración perimetral interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Cuadro de diálogo especificar configuración perimetral interna")  

7.  En **	Especificar perímetro externo**, escriba la información del FQDN de conferencia web del servidor perimetral.
    
    <div>
    

    > [!IMPORTANT]  
    > Antes de hacer clic en <STRONG>Siguiente</STRONG>, realice el próximo paso de este procedimiento. Es muy importante que no omita este paso.

    
    </div>

8.  Active la casilla **este grupo de servidores perimetrales se usa para la Federación y la conectividad de mensajería instantánea pública** si tiene previsto usar el servidor perimetral de Office Communications Server 2007 R2 heredado para la Federación. Si tiene varios servidores perimetrales implementados, solamente uno de ellos estará habilitado para la federación. Si no activa esta casilla y decide más adelante que desea habilitar la federación, deberá ejecutar de nuevo el asistente para combinar del Generador de topologías y volver a publicar la topología.
    
    ![Cuadro de diálogo servidor perimetral, especificar página perimetral externa](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página perimetral externa")  

9.  En **Especificar próximo salto**, escriba el nombre de dominio completo de la ubicación del próximo salto en el entorno. Haga clic en **Finalizar**.
    
    ![Cuadro de diálogo servidor perimetral, especificar página de salto siguiente](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página de salto siguiente")  

10. En **especificar configuración perimetral**, si se han agregado todos los servidores perimetrales de Office Communications Server 2007 R2, haga clic en **siguiente**. Si tiene más servidores perimetrales de Office Communications Server 2007 R2 para agregar, repita este procedimiento desde el paso 4.

11. En **especificar puerto SIP interno** , seleccione la opción predeterminada (es decir, si no modificó el puerto SIP predeterminado). Cambie esta opción como sea necesario si no usa el puerto predeterminado 5061 y haga clic en **Siguiente**.

12. En **Resumen**, haga clic en **Siguiente** para comenzar a combinar las topologías.

13. La página del asistente comprueba que la combinación de topologías se ha realizado correctamente.

14. En la columna **Estado**, verifique que el valor es **Correcto** y haga clic en **Finalizar**.

15. En el panel izquierdo del generador de topologías, ahora debería ver el **BackCompatSite**, que indica que el entorno de Office Communications Server 2007 R2 se ha combinado con Lync Server 2013.
    
    ![Generador de topologías que muestra una topología combinada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generador de topologías que muestra una topología combinada")  

16. En el menú **Acción**, haga clic en **Publicar topología** y en **Siguiente**.

17. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Es importante que complete el siguiente tema, <A href="import-policies-and-settings.md">Import policies and Settings</A>, para asegurarse de que la configuración de directivas heredada se importa en Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

