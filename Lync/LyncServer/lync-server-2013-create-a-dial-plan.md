---
title: 'Lync Server 2013: crear un plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 382b04f9b0aa835d0230cb05fb56cb272546c038
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Crear un plan de marcado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-24_

Para crear un plan de marcado nuevo, siga los pasos del procedimiento a continuación. Si desea editar un plan de marcado, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>Para crear un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.

4.  En la página **Plan de marcado**, haga clic en **Nuevo** y seleccione un ámbito para el plan de marcado:
    
      - **Plan de marcado de sitio** se aplica a un sitio en su totalidad, salvo a los usuarios o grupos que estén asignados a un plan de marcado de usuario. Si selecciona **Sitio** para el ámbito de un plan de marcado, debe elegir el sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se ha creado un plan de marcado, el sitio no aparece en el cuadro de diálogo **Seleccionar un sitio**.
    
      - **Plan de marcado de grupo** se puede aplicar a una puerta de enlace de red telefónica conmutada (RTC) o a un registrador. Si selecciona **Grupo** para el ámbito de un plan de marcado, elija la puerta de enlace de RTC o el registrador en el cuadro de diálogo **Seleccionar un servicio**. Si ya se ha creado un plan de marcado para un servicio (puerta de enlace de RTC o registrador), el servicio no aparece en la lista.
    
      - **Plan de marcado de usuario** se puede aplicar a usuarios o grupos especificados.
    
    <div>
    

    > [!NOTE]  
    > Una vez seleccionado el ámbito del plan de marcado, no se podrá cambiar.

    
    </div>

5.  Si está creando un plan de marcado de usuario, escriba un nombre descriptivo en el campo **Nombre** en el cuadro de diálogo **Plan de marcado nuevo**. Una vez se haya guardado este nombre, no se podrá cambiar.
    
    <div>
    

    > [!NOTE]  
    > Respecto a los planes de marcado de sitio, el campo <STRONG>Nombre</STRONG> se cumplimenta previamente con el nombre del sitio y no se puede modificar.<BR>Respecto a los planes de marcado de grupo, el campo <STRONG>Nombre</STRONG> se cumplimenta previamente con la puerta de enlace de RTC o el registrador y no se puede modificar.

    
    </div>

6.  El campo **Nombre simple** se cumplimenta previamente con el mismo nombre que aparece en el campo **Nombre**. Opcionalmente, puede editar este campo para especificar un nombre más descriptivo que defina el sitio, servicio o usuario al que se aplica el plan de marcado.
    
    <div>
    

    > [!IMPORTANT]  
    > El <STRONG>nombre simple</STRONG> debe ser único entre todos los planes de marcado de la implementación de Lync Server. No puede superar los 256 caracteres Unicode, que pueden ser caracteres alfabéticos o numéricos, un guión (-), un punto (.) o un carácter de subrayado (_).<BR>Caracteres <STRONG>no admitidos</STRONG> incluyen espacios y caracteres reservados tal y como se definenhttp://www.ietf.org/rfc/rfc3966.txt)en RFC 3966 (. Los caracteres reservados que <STRONG>no se admiten</STRONG> en el <STRONG>nombre simple</STRONG> son los siguientes:<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  (Opcional) En el campo **Descripción**, puede escribir información descriptiva adicional sobre el plan de marcado.

8.  (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.
    
    <div>
    

    > [!NOTE]  
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.

    
    </div>

9.  (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (\#, \*y 0-9).
    
    <div>
    

    > [!NOTE]  
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.

    
    </div>

10. Asocie y configure reglas de normalización para el plan de marcado tal como sigue:
    
      - Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**. Para obtener más información sobre cómo editar la regla, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**. Para obtener más información sobre cómo editar la copia, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <div>
    

    > [!NOTE]  
    > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación referente a la planeación.

    
    </div>

11. Compruebe que las reglas de normalización del plan de marcado están dispuestas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server recorre la lista de reglas de normalización de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.<BR>La regla de normalización predeterminada de <STRONG>guardar todas</STRONG> las reglas de normalización <STRONG>^ ({11}\d) $</STRONG> coincide con cualquier número de 11 dígitos. Por ejemplo, si agrega una regla de normalización que coincide con los números de 11 dígitos que comienzan por 1425, asegúrese de que <STRONG>mantener todas</STRONG> se ordena por debajo de la regla <STRONG>^ (1425 \{7}d) $</STRONG> más restrictiva.

    
    </div>

12. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

13. Haga clic en **Aceptar**.

14. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree un plan de marcado, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definición de reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

