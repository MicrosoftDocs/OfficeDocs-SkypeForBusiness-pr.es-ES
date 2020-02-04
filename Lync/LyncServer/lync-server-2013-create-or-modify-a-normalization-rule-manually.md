---
title: 'Lync Server 2013: Crear o modificar una regla de normalización manualmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Crear o modificar una regla de normalización manualmente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Complete los pasos siguientes si desea crear o modificar una regla de normalización de forma manual. Si desea crear o modificar una regla de normalización mediante la creación de una regla de normalización en el panel de control de Lync Server, vea [crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Para definir una regla de normalización de forma manual

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Faculta Siga los pasos que se indican en [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) o [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, asigne a la regla de normalización el nombre **5DigitExtension**).

5.  (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

6.  En **Crear regla de normalización**, haga clic en **Editar**.

7.  Especifique lo siguiente en **Escribir una expresión regular**:
    
      - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    
      - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.
    
    Por ejemplo, si introduce **\\^ (d{7}) $** en **coincidir con este patrón** y **+ 1425 $1** en la **regla de traducción**, la regla normaliza 5550100 a + 14255550100.

8.  (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

9.  (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

10. Haga clic en **Aceptar** para guardar la regla de normalización.

11. Haga clic en **Aceptar** para guardar el plan de marcado.

12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Cuando cree o cambie una regla de normalización, debe ejecutar el
comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

