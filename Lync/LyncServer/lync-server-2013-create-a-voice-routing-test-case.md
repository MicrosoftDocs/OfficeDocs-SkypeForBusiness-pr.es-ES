---
title: 'Lync Server 2013: Crear un caso de prueba de enrutamiento de voz'
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
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Crear un caso de prueba de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Para crear un caso de prueba

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **enrutamiento de voz** y luego en **probar enrutamiento de voz**.

4.  En la página **probar enrutamiento de voz** , haga clic en **nuevo** para crear un nuevo caso de prueba.

5.  En **nombre**, escriba un nombre único para el caso de prueba.
    
    El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial. Puede tener hasta 32 caracteres de longitud y puede contener cualquier carácter alfanumérico, además de la barra invertida (\\), el punto (.) o el carácter de subrayado (\_).

6.  En **número marcado para probar**, escriba el número marcado que desea usar para probar la configuración de enrutamiento que especifique para este caso de prueba. En función del plan de marcado, la ruta y la Directiva de voz, este número se normalizará y se mostrará como salida.

7.  En la lista **plan de marcado** , seleccione el plan de marcado que se usará al ejecutar la prueba. El valor predeterminado es el plan de marcado global.

8.  En la lista **Directiva de voz** , seleccione la Directiva de voz que se va a usar al ejecutar la prueba. El valor predeterminado es la Directiva de voz global.

9.  En **traducción prevista**, escriba el número de teléfono en el formato que espera verlo después de la traducción. Este es el valor del número de teléfono que está probando después de que se haya traducido con la primera regla de normalización que coincida en el plan de marcado seleccionado. Al ejecutar el caso de prueba, si el número que está probando no da como resultado el valor de la **traducción esperada**, se producirá un error en la prueba.

10. Faculta En la lista de **uso de RTC esperada** , puede seleccionar el registro de uso de la red de telefonía conmutada (RTC) que espera que se use al ejecutar el caso de prueba, en función del plan de marcado y la Directiva de voz especificados. Si se usa un registro de uso de RTC diferente, se produce un error en la prueba.

11. Faculta En la lista de **rutas esperadas** , puede seleccionar la ruta de voz que espera que se use al ejecutar el caso de prueba, en función del plan de marcado y la Directiva de voz especificados. Si se usa una ruta de voz diferente, se produce un error en la prueba.

12. Faculta Haga clic en **Ejecutar** para ejecutar el caso de prueba. Los resultados se muestran en el panel derecho de la página.

13. Haga clic en **Aceptar**.

14. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>
    
    Si el plan de marcado que se está usando en la prueba normaliza los números de teléfono que comienzan con un signo más (por ejemplo, + 12065551219), ese plan puede provocar errores en la prueba de enrutamiento de voz. (El plan de marcado y la ruta de voz funcionan; de hecho, test-CsDialPlan se realizará correctamente. Sin embargo, la prueba de enrutamiento de voz podría fallar.) Esto es algo que se debe tener en cuenta al probar las rutas de voz.

</div>

<div>

## <a name="see-also"></a>Vea también


[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

