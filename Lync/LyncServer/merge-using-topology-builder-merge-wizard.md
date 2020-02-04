---
title: Combinar mediante el Asistente para combinar generador de topología
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
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Combinar mediante el Asistente para combinar generador de topología

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

1.  Descargue la implementación existente con el generador de topología.

2.  En el menú **acción** , seleccione **combinar Office Communications Server 2007 R2**.

3.  Haga clic en **Siguiente**.

4.  En **especificar configuración perimetral**, haga clic en **Agregar**.
    
    ![Asistente para combinar topología, especificar página de configuración de Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración de Edge")  

5.  En **especificar tipo de borde**, escriba el tipo de configuración del servidor perimetral y, a continuación, haga clic en **siguiente**. En este ejemplo se usa la opción de **servidor de borde único** .
    
    <div>
    

    > [!IMPORTANT]  
    > La <STRONG>implementación de bordes expandida</STRONG> no es una configuración admitida. Un <STRONG>servidor perimetral expandido</STRONG> debe convertirse primero en un <STRONG>único servidor perimetral</STRONG> o en un servidor <STRONG>perimetral consolidado de carga equilibrada</STRONG> .

    
    </div>

6.  En **especificar la configuración de borde interno** , escriba la información relevante para el FQDN y los puertos internos del grupo de límites según sea necesario y, a continuación, haga clic en **siguiente**.
    
    ![Especificar el cuadro de diálogo Configuración de borde interno](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Especificar el cuadro de diálogo Configuración de borde interno")  

7.  En **especificar borde externo**, escriba la información de FQDN de conferencias web para su servidor perimetral.
    
    <div>
    

    > [!IMPORTANT]  
    > Antes de hacer clic en <STRONG>siguiente</STRONG>, siga el paso siguiente de este procedimiento. Es muy importante que no pierdas este paso.

    
    </div>

8.  Active la casilla **este grupo de bordes se usa para la Federación y conectividad de mensajería instantánea pública** si planea usar el servidor perimetral de Office Communications Server 2007 R2 heredado para la Federación. Si tiene varios servidores perimetrales implementados, solo uno de ellos estará habilitado para la Federación. Si no activa esta casilla y decide más tarde que desea habilitar la Federación, debe ejecutar el Asistente para la combinación del generador de topología y volver a publicar su topología.
    
    ![Cuadro de diálogo servidor perimetral, especificar página de borde externo](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página de borde externo")  

9.  En **especificar el siguiente salto**, escriba el nombre de dominio completo (FQDN) de la ubicación del próximo salto en su entorno. Haga clic en **Finalizar**.
    
    ![Cuadro de diálogo servidor perimetral, especificar página de próximo salto](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Cuadro de diálogo servidor perimetral, especificar página de próximo salto")  

10. En **especificar la configuración perimetral**, si se han agregado todos los servidores perimetrales de Office Communications Server 2007 R2, haga clic en **siguiente**. Si tiene más servidores perimetrales de Office Communications Server 2007 R2 para agregar, repita este procedimiento a partir del paso 4.

11. En **especificar puerto SIP interno** , seleccione la configuración predeterminada (es decir, si no modificó el puerto SIP predeterminado). Cambie según corresponda si no usa un puerto predeterminado de 5061 y, a continuación, haga clic en **siguiente**.

12. En **Resumen**, haga clic en **siguiente** para empezar a combinar las topologías.

13. La página del asistente verifica que la combinación de las topologías se haya realizado correctamente.

14. En la columna **Estado** , compruebe que el valor es **correcto**y, a continuación, haga clic en **Finalizar**.

15. En el panel izquierdo del generador de topología, ahora debe ver el **BackCompatSite**, que indica que el entorno de Office Communications Server 2007 R2 se ha fusionado con Lync Server 2013.
    
    ![Generador de topología que muestra una topología combinada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generador de topología que muestra una topología combinada")  

16. En el menú **acción** , haga clic en **publicar topología**y, a continuación, haga clic en **siguiente**.

17. Cuando finalice el **Asistente para la publicación** , haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Es importante que complete el tema siguiente, <A href="import-policies-and-settings.md">importar directivas y configuración</A>, para asegurarse de que la configuración de directiva heredada se importa a Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

