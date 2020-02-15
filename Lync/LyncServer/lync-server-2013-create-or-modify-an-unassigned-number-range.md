---
title: 'Lync Server 2013: crear o modificar un intervalo de números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b9f35157b4172376cdcb4724346dc7cd9ecbcf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Crear o modificar un intervalo numérico sin asignar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Use uno de los siguientes procedimientos para configurar intervalos numéricos sin asignar para la aplicación de anuncio.

<div>


> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar el panel de control de Lync Server para configurar números de teléfono sin asignar

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.

4.  En la página **Número sin asignar**, siga uno de estos procedimientos:
    
      - Para crear un nuevo intervalo de números, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.
        
        <div>
        

        > [!NOTE]  
        > Una vez haya confirmado el nuevo intervalo de números sin asignar para la base de datos, no podrá cambiar este nombre.

        
        </div>
    
      - Para modificar un intervalo de números existentes, escriba en el campo de búsqueda todo el intervalo de números o parte de él. En la lista de intervalos numéricos resultante, haga clic en el nombre que desee, en **Editar** y en **Mostrar detalles**.

5.  En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo, y en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>El número inicial del intervalo debe ser menor o igual al número final del intervalo.</P>
    > <LI>
    > <P>Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</P>
    > <LI>
    > <P>El número debe coincidir con la expresión regular (Tel:) ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. Esto significa que el número puede comenzar con la cadena de caracteres tel: (si no especifica la cadena de caracteres, se agregará automáticamente), un signo más (+), y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".</P></LI></UL>

    
    </div>

6.  En **Servicio de anuncio**, lleve a cabo uno de los siguientes procedimientos:
    
      - Haga clic en **Anuncio**.
    
      - Haga clic en **Mensajería unificada de Exchange**.

7.  Si, en el paso anterior, ha hecho clic en **Anuncio**, proceda de la siguiente manera:
    
    1.  En **FQDN del servidor de destino**, haga clic en **Seleccionar**, haga clic en el Id. de servicio del servicio de aplicaciones que ejecute la aplicación Anuncio que se va a encargar de las llamadas entrantes correspondientes a este intervalo de números sin asignar y, a continuación, haga clic en **Aceptar**.
    
    2.  En **Anuncio**, haga clic en el anuncio que se va a reproducir para este intervalo de números sin asignar.

8.  Si, en el paso anterior, hizo clic en **Mensajería unificada de Exchange**, en **Número de teléfono del operador automático**, haga clic en **Seleccionar**, haga clic en el número de teléfono que se va a utilizar para este intervalo de números sin asignar y, a continuación, en **Aceptar**.

9.  Haga clic en **Aceptar**.

10. En la página **Número sin asignar**, asegúrese de que los intervalos de números sin asignar se disponen según el orden que desee. Para cambiar la posición de un intervalo en la tabla, haga clic en uno o más nombres consecutivos en la lista de intervalos y, a continuación, haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!TIP]  
    > Lync Server busca la tabla de números sin asignar de arriba abajo y usa el primer intervalo que coincide con el número sin asignar. Si tiene intervalos superpuestos y un intervalo especifica una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.

    
    </div>

11. Cuando haya ordenado el intervalo de números sin asignar según su conveniencia, haga clic en **Confirmar todo**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Para usar Windows PowerShell para configurar números de teléfono sin asignar

1.  Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Use **New-CsUnassignedNumber** para crear un nuevo intervalo de números no asignados. Use **Set-CsUnassignedNumber** para modificar un intervalo de números no asignados existente.
    
    <div>
    

    > [!TIP]  
    > Si tiene intervalos solapados y desea que se apliquen en un orden específico, incluya el parámetro Prioridad. Se aplicará a la llamada el intervalo con la máxima prioridad.

    
    </div>
    
    En la línea de comandos, realice una de las acciones siguientes:
    
      - Si desea crear un intervalo de números para un servicio de anuncio, ejecute:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - O, si desea crear un intervalo de números para el Operador automático de mensajería unificada de Exchange, ejecute:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Por ejemplo:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    O bien
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    El siguiente ejemplo muestra cómo modificar los números de un intervalo de números no asignados existente:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

