---
title: 'Lync Server 2013: ejecutar pruebas de enrutamiento de voz informal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Ejecutar pruebas de enrutamiento de voz informal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

Puede usar el cuadro de diálogo **crear información de caso de prueba de enrutamiento de voz** para ejecutar pruebas informales antes de crear un caso de prueba real. Cuando esté satisfecho con el resultado de una prueba, tiene la opción de guardarla como caso de prueba formal.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>Para ejecutar una prueba de enrutamiento de voz informal

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **enrutamiento de voz**y, a continuación, en **probar enrutamiento de voz**.

4.  En la página **probar enrutamiento de voz** , haga clic en **crear ruta de voz información del caso de prueba**.

5.  En el campo **número marcado** , escriba el número de teléfono que desea usar para esta prueba. Este número se normalizará y se mostrará en el campo **Número normalizado** del panel **resultados** .

6.  En la lista **plan de marcado** , seleccione el plan de marcado que se va a usar para probar el número marcado. El valor predeterminado es el plan de marcado global.
    
    Al ejecutar la prueba, la primera regla de normalización del plan de marcado que coincida con el número marcado se mostrará en el campo **regla** de normalización del panel **resultados** .

7.  En la lista **Directiva de voz** , seleccione la Directiva de voz que se va a usar para probar el número marcado. El valor predeterminado es la Directiva de voz global.
    
    Al ejecutar la prueba, se mostrará el primer registro de uso de RTC coincidente en esta directiva de voz en el **primer campo uso de RTC** del panel **resultados** . Además, la primera ruta de voz coincidente asociada con este registro de uso de RTC se mostrará en el **primer** campo de ruta.

8.  Faculta Active la casilla de verificación rellenar **desde el usuario** si desea probar el número marcado con la Directiva de voz asignada a un usuario en particular.
    
    1.  Haga clic en **examinar** para mostrar el cuadro de diálogo **Seleccionar usuarios de voz de empresa** .
    
    2.  Haga clic en **Buscar** para mostrar la lista de usuarios que están habilitados para telefonía IP empresarial.
    
    3.  Haga doble clic en el nombre de usuario cuya directiva de voz asignada desea usar para esta prueba. El campo de **Directiva** se rellena con la Directiva de voz asignada al usuario seleccionado.
    
    Al ejecutar la prueba, se mostrará el primer registro de uso de la red telefónica conmutada (RTC) en esta directiva de voz en el primer campo de **uso de RTC** del panel **resultados** . Además, la primera ruta de voz coincidente asociada con este registro de uso de RTC se mostrará en el **primer** campo de ruta.

9.  Haga clic en **Ejecutar** para ejecutar el caso de prueba. Los resultados se muestran en el panel derecho del cuadro de diálogo.

10. Faculta Haga clic en **Guardar como** si desea guardar esta configuración de prueba como un caso de prueba formal.
    
    1.  En el campo **nombre** del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz** , escriba un nombre único para el caso de prueba.
        
        El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial. Puede tener hasta 32 caracteres de longitud y puede contener cualquier carácter alfanumérico, además de la barra invertida (\\), el punto (.) o el carácter de subrayado (\_).
    
    2.  Tenga en cuenta que los campos restantes en el cuadro de diálogo **Guardar información del caso de prueba de enrutamiento de voz** son de solo lectura y se rellenan previamente desde la configuración de prueba informal *y* los resultados. Compruebe que esta es la configuración que desea guardar para el caso de prueba.
        
        <div>
        

        > [!NOTE]  
        > Los valores de los resultados de la prueba se usan para rellenar previamente los campos en el cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG> de la siguiente manera: 
        > <UL>
        > <LI>
        > <P>La <STRONG>traducción esperada</STRONG> se rellena previamente con el valor del campo de <STRONG>Número normalizado</STRONG> .</P>
        > <LI>
        > <P>La <STRONG>ruta esperada</STRONG> se ha rellenado previamente con el valor del primer campo de <STRONG>ruta</STRONG> .</P>
        > <LI>
        > <P>El <STRONG>registro de uso de RTC esperado</STRONG> se rellenó con el valor en el <STRONG>primer campo uso de RTC</STRONG> .</P></LI></UL>Si durante la ejecución de prueba no se encontraron coincidencias para cualquiera de estos valores, el campo correspondiente estará vacío en el cuadro de diálogo <STRONG>Guardar información del caso de prueba de enrutamiento de voz</STRONG> .

        
        </div>
    
    3.  Haga clic en **Aceptar** para guardar el caso de prueba, o haga clic en **Cancelar** para volver al cuadro de diálogo **ver información del caso de prueba de enrutamiento de voz** para seguir desarrollando la prueba antes de guardarla.

11. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el caso de prueba. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear un caso de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Ejecutar los casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
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

