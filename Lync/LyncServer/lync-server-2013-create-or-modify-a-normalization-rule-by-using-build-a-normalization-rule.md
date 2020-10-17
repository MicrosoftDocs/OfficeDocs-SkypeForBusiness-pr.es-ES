---
title: Creación o modificación de una regla de normalización mediante la creación de una regla de normalización
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d4c6d5b8a8cd53cee9fdae0a38769a535b118
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508847"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Crear o modificar una regla de normalización con la creación de una regla de normalización en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Complete los pasos siguientes si desea crear o modificar una regla de normalización en el panel de control de Lync Server. Como alternativa, si desea crear o modificar una regla de normalización manualmente, vea [crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Para definir una regla mediante Generar regla de normalización

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Opcional Siga los pasos que se indican en [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) hasta el paso 11 o [modificar un plan de marcado en Lync Server 2013 hasta el](lync-server-2013-modify-a-dial-plan.md) paso 10.

4.  En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **Extension5digitos**).

5.  (Opcional) En **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

6.  En **Generar regla de normalización**, escriba valores en los siguientes campos:
    
      - **Dígitos iniciales**     Opcional Especifique los dígitos iniciales de los números marcados a los que desea que corresponda el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    
      - **Longitud**     Especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con esta longitud, que coincida con números marcados que tengan como mínimo esta longitud o que coincidan con números marcados de cualquier longitud.
    
      - **Dígitos que se van a quitar**     Opcional Especifique el número de dígitos iniciales que se quitarán de los números marcados con los que desea que se ajuste la trama.
    
      - **Dígitos que se van a agregar**     Opcional Especifique los dígitos que se agregarán a los números marcados con los que desea que se ajuste la trama.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si deja en blanco **Dígitos iniciales**, escriba **7** en el campo **Longitud** y seleccione **Exactamente**, e introduzca **0** en **Dígitos que se quitarán**, la expresión regular que se creará como resultado en **Patrón con el que hacer coincidir** es:
    
    **^ ( \\ d {7} ) $**

7.  En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:
    
      - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es **^ ( \\ d {7} ) $** , **$1** en la regla de conversión representa los números marcados de 7 dígitos.
    
      - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425**).
    
    Por ejemplo, si el **patrón que debe coincidir** contiene **^ ( \\ d {7} ) $** como patrón para los números marcados y la **regla de conversión** contiene **+ 1425 $1** como modelo para los números de teléfono e. 164, la regla normaliza 5550100 a + 14255550100.

8.  (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

9.  (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    <div>
    

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

10. Haga clic en **Aceptar** para guardar la regla de normalización.

11. Haga clic en **Aceptar** para guardar el plan de marcado.

12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

