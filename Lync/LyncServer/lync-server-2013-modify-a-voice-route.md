---
title: 'Lync Server 2013: modificar una ruta de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86c64b9cc595c108676a519bc98cba3ecad04a62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a>Modificar una ruta de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En este tema se describe cómo editar una ruta de voz. Para crear una ruta nueva, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## <a name="to-modify-a-voice-route"></a>Para modificar una ruta de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.

4.  En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
      - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
      - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.

6.  (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.

7.  Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
      - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:
        
          - **Dígitos iniciales para los números que desea permitir:** Escriba los valores de prefijo que debe acomodar esta ruta (incluido el + inicial + si es necesario). Por ejemplo, escriba **+425** y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
        
          - **Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **excepciones**. Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta. Por ejemplo, para excluir números que empiecen por + 425237 de la ruta, escriba un valor de **+ 425237** en el campo **excepciones** y, a continuación, haga clic en **Aceptar**.
    
      - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener información sobre cómo escribir expresiones regulares, consulte "expresiones regulares de .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)en.

8.  Seleccione **suprimir identificador de llamada** si no desea que el identificador del teléfono que hace la llamada saliente aparezca al destinatario de la llamada. Si selecciona esta opción, debe especificar un identificador de **llamada alternativo** que aparecerá en la presentación del identificador de llamada del destinatario.

9.  Para asociar uno o más troncos de red telefónica conmutada (RTC) con la ruta de voz, haga clic en **Agregar**y, a continuación, seleccione un tronco de la lista.
    
    <div>
    

    > [!NOTE]  
    > Si la implementación incluye servidores de mediación de Microsoft Office Communications Server 2007 R2, también estarán disponibles en la lista.

    
    </div>

10. Para asociar uno o más usos de RTC con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.
    
    <div>
    

    > [!NOTE]  
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.<BR>Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A>.

    
    </div>

11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!NOTE]  
    > En contraste con una directiva de voz en la que el orden en que se enumeran los registros de uso de RTC es importante, el orden de los registros de uso de RTC en una ruta de voz es insignificante. Sin embargo, se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server recorre la lista de arriba abajo).

    
    </div>

12. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar una ruta de voz que no haya pasado la prueba aún y volver a configurarla más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

13. Haga clic en **Aceptar**.

14. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree o modifique una ruta de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
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

