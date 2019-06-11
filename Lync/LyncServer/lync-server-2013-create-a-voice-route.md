---
title: 'Lync Server 2013: crear una ruta de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Crear una ruta de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En el procedimiento siguiente se explica cómo crear una nueva ruta de voz con el panel de control de Lync Server 2013. Para editar una ruta existente, vea el procedimiento sobre cómo [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md) .

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Para crear una ruta de voz con el panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  Haga clic en **Ruta**.

5.  Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.

6.  En el campo **Nombre**, escriba un nombre descriptivo para la ruta de voz.

7.  (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.

8.  Para especificar los patrones que desea que incluya esta ruta, puede usar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
      - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
        
          - **Dígitos iniciales para los números que desea permitir:** Escriba los valores de prefijo que esta ruta debe acomodar (incluido el +, si es necesario). Por ejemplo, escriba **+425** y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
        
          - **Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **excepciones**. Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta. Por ejemplo, para excluir los números que comiencen por de la ruta, escriba el valor **+425237** campo **Excepciones** y, a continuación, haga clic en **Aceptar**.
    
      - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener más información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)" en.

9.  Seleccione **Suprimir Id. de autor de llamada** si no desea que el Id. del teléfono desde donde se efectúa la llamada saliente se muestre al receptor de la llamada. Si selecciona esta opción, es preciso que especifique un **Id. de autor de llamada alternativo** que aparecerá en la pantalla que contiene el Id. del autor de la llamada del destinatario.

10. Para asociar uno o más troncos a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
    <div>
    

    > [!NOTE]  
    > Si su implementación incluye servidores de mediación de Microsoft Office Communications Server 2007 R2, también estarán disponibles en la lista.

    
    </div>

11. Para asociar uno o varios usos de la red telefónica conmutada (RTC) con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.
    
    <div>
    

    > [!NOTE]  
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.<BR>Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar los registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</A>.

    
    </div>

12. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!NOTE]  
    > En contraste con una directiva de voz, donde el orden en el que se muestran los registros de uso de RTC es importante, el orden en que aparecen los registros de uso de RTC en la ruta de voz es inimportante. Sin embargo, le recomendamos que organice la lista según la frecuencia de uso. Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server recorre la lista desde el principio).

    
    </div>

13. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar una ruta de voz que aún no pase la prueba y, a continuación, volver a configurarla más tarde. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

14. Haga clic en **Aceptar** para guardar la ruta de voz.

<div>


> [!IMPORTANT]  
> Al crear una ruta de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Ver los registros de uso de RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

