---
title: 'Lync Server 2013: modificar un plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db84f9b353450419a8cc8029e4a24d01f0df76b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534417"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modificar un plan de marcado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Para modificar un plan de marcado existente, siga los pasos del procedimiento a continuación. Si desea crear un nuevo plan de marcado, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Para modificar un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en  **Enrutamiento de voz ** y, a continuación, en  **Plan de marcado **.

4.  En la página **Plan de marcado**, haga doble clic en el nombre del plan de marcado.
    
    <div>
    

    > [!NOTE]  
    > El ámbito y el nombre del plan de marcado se establecieron cuando se creó el plan de marcado. No pueden modificarse.

    
    </div>

5.  (Opcional) En **Editar plan de marcado**, edite el campo **Nombre simple**, el cual se ha cumplimentado previamente con el mismo nombre que aparece en el campo **Nombre** para especificar un nombre más descriptivo que refleje el sitio, el servicio o el usuario a quien se aplica el plan de marcado.
    
    <div>
    

    > [!IMPORTANT]  
    > El <STRONG>nombre simple</STRONG> debe ser único entre todos los planes de marcado de la implementación de Lync Server 2013. No puede exceder de 256 caracteres Unicode, donde cada uno de los cuales puede ser alfanumérico o numérico, un guión (-), un punto (.), un signo más (+) o un guión bajo (_).<BR>No se permiten espacios en el campo <STRONG>Nombre simple</STRONG>.

    
    </div>

6.  (Opcional) En el campo **Descripción**, escriba información descriptiva sobre el plan de marcado.

7.  (Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.
    
    <div>
    

    > [!NOTE]  
    > Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.

    
    </div>

8.  (Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9). Puede escribir un valor de prefijo de hasta cuatro caracteres (es decir,, \# \* y 0-9).
    
    <div>
    

    > [!NOTE]  
    > Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.

    
    </div>

9.  Asocie y configure reglas de normalización para el plan de marcado:
    
      - Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En el cuadro de diálogo **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**. Para obtener más información sobre cómo editar la regla, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**. Para obtener más información sobre cómo editar la copia, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <div>
    

    > [!NOTE]  
    > Cada plan de marcado debe tener al menos una regla de normalización asociada. Para obtener más información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación referente a la planeación.

    
    </div>

10. Compruebe que las reglas de normalización del plan de marcado están dispuestas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server recorre la lista de reglas de normalización de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.<BR>La regla de normalización predeterminada de <STRONG>guardar todas</STRONG> las reglas de normalización <STRONG>^ (\d {11} ) $</STRONG> coincide con cualquier número de 11 dígitos. Si, por ejemplo, agrega una regla de normalización que coincide con los números de 11 dígitos que comienzan por 1425, asegúrese de que la regla <STRONG>mantener todos</STRONG> está ordenada por debajo de la regla <STRONG>^ (1425 \ d {7} ) $</STRONG> más restrictiva.

    
    </div>

11. (Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

12. Haga clic en **Aceptar**.

13. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree o modifique un plan de marcado, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definición de reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

