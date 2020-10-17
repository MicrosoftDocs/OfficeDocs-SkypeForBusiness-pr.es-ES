---
title: 'Lync Server 2013: crear o modificar un número de acceso de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19766eb4abf5a386155e5494accb1edd17afb14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516887"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Crear o modificar un número de acceso de conferencia de acceso telefónico local en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Siga estos pasos si desea crear o modificar un número de acceso de conferencia de acceso telefónico local.

<div>


> [!IMPORTANT]  
> Antes de crear un nuevo número de acceso telefónico local, debe establecer una región de conferencia de acceso telefónico local en el plan de marcado asociado con el nuevo número de acceso telefónico. Varios planes de marcado pueden usar la misma región.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Para crear o modificar un número de acceso telefónico local

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.

4.  En la página **número de acceso telefónico local** , siga uno de estos procedimientos:
    
      - Haga clic en **nuevo** para abrir **un nuevo número de acceso telefónico local**.
    
      - Haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
        
        <div>
        

        > [!NOTE]  
        > Si se usa el campo de búsqueda para buscar el contenido de una columna en la lista de números de acceso telefónico a redes, es posible que no ofrezca los resultados esperados. En su lugar, ordene la lista por la columna de interés para identificar el número de acceso telefónico que desea ver o cambiar.

        
        </div>

5.  En **número para mostrar**, escriba el número de teléfono que los usuarios de teléfono de la red telefónica conmutada (RTC) llaman para unirse a una conferencia.
    
    <div>
    

    > [!NOTE]  
    > Este número se muestra en las invitaciones a la reunión y en la Página Web de configuración de conferencia de acceso telefónico local.

    
    </div>

6.  En **nombre para mostrar**, escriba una descripción para el número de acceso telefónico local. Este es el nombre que se asocia con el número de acceso telefónico local en los resultados de la búsqueda de Lync.
    
    <div>
    

    > [!NOTE]  
    > Este nombre se muestra en el cliente cuando un usuario llama al número de acceso.

    
    </div>

7.  En **URI de línea**, escriba el número E. 164 del número de acceso telefónico en formato URI de Tel, incluido el símbolo + delante del número y excluidos los espacios. Por ejemplo, Tel: + 14255550200.
    
    <div>
    

    > [!NOTE]  
    > El mismo URI de línea no puede volver a usarse por otro número de acceso de conferencia de acceso telefónico local.

    
    </div>

8.  En **URI del SIP**, haga lo siguiente:
    
      - En el cuadro de texto, escriba un URI de SIP único para este número de acceso de conferencia de acceso telefónico local. Este URI de SIP se muestra en varias ubicaciones, incluidos, entre otros, los mensajes de notificación de llamadas y las versiones anteriores de clientes de Communicator.
        
        <div>
        

        > [!NOTE]  
        > El mismo URI de SIP no puede volver a usarse por otro número de acceso de conferencia de acceso telefónico local. El URI del SIP no se puede modificar una vez que se ha creado el número de acceso. La única forma de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.

        
        </div>
    
      - En el cuadro de lista desplegable, haga clic en el dominio de la aplicación operador de conferencia que admite este número de acceso telefónico.

9.  En **Grupo**, haga clic en el grupo de servidores que ejecuta la instancia del operador de conferencia que admite este número de acceso telefónico.
    
    <div>
    

    > [!NOTE]  
    > Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> o eliminar y volver a crear el número de acceso.

    
    </div>

10. En **idioma principal**, haga clic en el idioma en el que se reproducen los mensajes para este número de acceso telefónico.
    
    <div>
    

    > [!NOTE]  
    > El idioma principal es el idioma que el operador de conferencia usa para responder a la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la Página Web de configuración de conferencia de acceso telefónico local.

    
    </div>

11. Opcional En **idiomas secundarios (un máximo de cuatro)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales para los que las personas que llaman deben ser compatibles con este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Puede elegir un máximo de cuatro idiomas secundarios para cada número de acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de escribir el identificador de conferencia al llamar a una conferencia.

    
    </div>

12. Para agregar una región para el número de acceso telefónico local, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones que estén asociadas a los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.

13. Para eliminar una región del número de acceso telefónico local, en **regiones asociadas**, haga clic en la región que desea eliminar y, a continuación, haga clic en **quitar**.

14. Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

