---
title: 'Lync Server 2013: crear un caso de prueba de enrutamiento de voz'
description: 'Lync Server 2013: crear un caso de prueba de enrutamiento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d81f4d39a6e3972ebf036fdaca59936f3f6b86bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562406"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Crear un caso de prueba de enrutamiento de voz en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Para crear un caso de prueba

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en **Nuevo** para crear un nuevo caso de prueba.

5.  En **Nombre**, escriba un nombre único para el caso de prueba.
    
    El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial. Puede tener hasta 32 caracteres de longitud y puede contener caracteres alfanuméricos, además de la barra diagonal inversa ( \\ ), el punto (.) o el carácter de subrayado ( \_ ).

6.  En **Número marcado para prueba**, escriba el número marcado que desea usar para probar la configuración de enrutamiento especificada para este caso de prueba. Según el plan de marcado, la ruta y la directiva de voz, este número se normalizará y se mostrará como resultado.

7.  En la lista **Plan de marcado**, seleccione el plan de marcado que se va a usar cuando se ejecute la prueba. El plan de marcado predeterminado es el plan de marcado Global.

8.  En la lista **Directiva de voz**, seleccione la directiva de voz que se va a usar cuando se ejecute la prueba. La directiva de voz predeterminada es la directiva de voz Global.

9.  En **Conversión prevista**, escriba el número de teléfono en el formato que desea que se muestre tras la conversión. Dicho número corresponde al valor del número de teléfono que se está probando tras la conversión de la primera regla de normalización que coincida con el plan de marcado seleccionado. Cuando ejecuta el caso de prueba, sabrá si ha fallo cuando el número que se está probando no se convierte en el valor especificado en **Conversión prevista**.

10. (Opcional) En la lista **Uso de RTC previsto**, puede seleccionar el registro de uso de la red telefónica conmutada (RTC) que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa un registro de uso de RTC diferente significa que la prueba ha fallado.

11. (Opcional) En la lista **Ruta prevista**, puede seleccionar la ruta de voz que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa una ruta de voz diferente significa que la prueba ha fallado.

12. (Opcional) Haga clic en **Ejecutar** para iniciar el caso de prueba. Los resultados se mostrarán en el panel que hay a la derecha de la página.

13. Haga clic en **Aceptar**.

14. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>
    
    Si el plan de marcado que se usa en la prueba normaliza los números de teléfono que comienzan con un signo más (por ejemplo, + 12065551219), es posible que se produzca un error en la prueba de enrutamiento de voz. (El plan de marcado y la ruta de voz funcionarán; de hecho, Test-CsDialPlan se realizarán correctamente. Sin embargo, es posible que se produzca un error en la prueba de enrutamiento de voz. Esto es algo que se debe tener en cuenta al probar las rutas de voz.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

