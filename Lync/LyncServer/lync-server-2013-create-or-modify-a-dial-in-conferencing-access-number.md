---
title: 'Lync Server 2013: Crear o modificar un número de acceso para conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Siga estos pasos si desea crear o modificar un número de acceso de conferencia de acceso telefónico local.

<div>


> [!IMPORTANT]  
> Antes de crear un nuevo número de acceso telefónico local, debe establecer una región de conferencia de acceso telefónico local en el plan de marcado asociado al nuevo número de acceso telefónico local. Varios planes de marcado pueden usar la misma región.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Para crear o modificar un número de acceso de acceso telefónico local

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.

4.  En la página **Número de acceso telefónico local**, siga uno de estos procedimientos:
    
      - Haga clic en **Nuevo** para abrir **Nuevo número de acceso telefónico local**.
    
      - Haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar** y después haga clic en **Mostrar detalles**.
        
        <div>
        

        > [!NOTE]  
        > Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar.

        
        </div>

5.  En **Número para mostrar**, escriba el número de teléfono que los usuarios de RTC (Red telefónica conmutada) marcan para unirse a una conferencia.
    
    <div>
    

    > [!NOTE]  
    > Este número se muestra en las invitaciones a reuniones y en la página web Configuración de la conferencia de acceso telefónico local.

    
    </div>

6.  En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico local. Este es el nombre que está asociado al número de acceso telefónico local en los resultados de la búsqueda de Lync.
    
    <div>
    

    > [!NOTE]  
    > Este número se muestra en el cliente cuando un usuario llama al número de acceso.

    
    </div>

7.  En **URI de línea**, escriba el número E.164 del número de acceso telefónico local en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel.: +14255550200.
    
    <div>
    

    > [!NOTE]  
    > El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias.

    
    </div>

8.  En **URI del SIP**, siga este procedimiento:
    
      - En el cuadro de texto, escriba un URI del SIP único para este número de acceso a conferencias de acceso telefónico local. Este URI del SIP se muestra en varias ubicaciones, entre las que se incluyen los mensajes de notificación de llamada y las versiones anteriores de clientes de Communicator.
        
        <div>
        

        > [!NOTE]  
        > El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.

        
        </div>
    
      - En el cuadro de lista desplegable, haga clic en el dominio de la aplicación de operador de conferencia que admite este número de acceso telefónico local.

9.  En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico local.
    
    <div>
    

    > [!NOTE]  
    > Si necesita cambiar el grupo de servidores tras crear el número de acceso, necesitará usar el cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> o eliminar y volver a crear el número de acceso.

    
    </div>

10. En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico local.
    
    <div>
    

    > [!NOTE]  
    > El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.

    
    </div>

11. (Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico local y luego haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.

    
    </div>

12. Para agregar una región para el número de acceso telefónico local, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones asociadas con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.

13. Para eliminar una región del número de acceso telefónico local, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.

14. Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

