---
title: 'Lync Server 2013: creación o modificación de una directiva de ubicación'
description: 'Lync Server 2013: crear o modificar una directiva de ubicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba097ddb6e4ca8515c1eb33ae9d7e033821aef31
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563006"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Creación o modificación de una directiva de ubicación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación de usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.

Puede configurar directivas de ubicación desde el grupo de **configuración de red** en el panel de control de Lync Server 2013. En el panel de control de Lync Server, puede ver, crear, modificar o eliminar directivas de ubicación. Use los procedimientos que se describen en esta sección para crear o modificar una directiva de ubicación. Para obtener más información sobre cómo eliminar directivas de ubicación, consulte [eliminar una directiva de ubicación en Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

En Lync Server 2013, puede invalidar la cantidad de tiempo predeterminada entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor predeterminado es 4 horas. Utilice el cmdlet **Set-CsLocationPolicy** con el parámetro LocationRefreshInterval para invalidar el valor predeterminado.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Para crear una nueva Directiva de ubicación en el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página  **Directiva de ubicación **, haga clic en  **Nuevo ** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, elija el sitio al que desea aplicar la directiva y haga clic en **Aceptar**. En la página **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Sitio**, y el campo **Nombre** contiene el nombre del sitio que ha elegido. No puede modificar ninguno de estos campos. Se aplicará automáticamente una directiva de sitio a todos los usuarios del sitio especificado y se invalidará la directiva global para dichos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Usuario**. No puede modificar este valor. En el campo **Nombre**, escriba el nombre que desea asignar a esta directiva. Las directivas de usuario no se aplican automáticamente a ningún usuario. Tras crear la directiva de usuario, debe otorgar automáticamente dicha directiva a los usuarios o los sitios de red a los que desea que se aplique.

5.  Rellene los campos restantes como se muestra a continuación:
    
      - **Habilitar los servicios**     de emergencia mejorados Active esta casilla para habilitar los usuarios asociados con esta directiva para E9-1-1. Cuando se habilitan los servicios de emergencia, los clientes de Lync Server recuperarán la información de ubicación en el registro y la incluirán cuando se realice una llamada de emergencia.
    
      - **Ubicación**     Especifique uno de los siguientes valores:
        
          - **Es necesario**     Se pedirá al usuario que escriba la información de ubicación cuando el cliente se registre en una nueva ubicación. El usuario puede anular la solicitud sin especificar ninguna información. Si se especifica información, primero responderá a la llamada de emergencia el proveedor de servicios de emergencia para verificar la ubicación antes de enrutar la llamada al operador PSAP (Punto de respuesta de seguridad pública), o lo que es lo mismo, al operador del 911.
        
          - **No es necesario**     No se pedirá al usuario una ubicación. Al realizar una llamada sin información de ubicación, el proveedor de servicios de emergencia responderá a la llamada y solicitará que se especifique una ubicación.
        
          - **Renuncia de responsabilidad**     Esta opción es la misma que **required** , excepto en que el usuario no puede descartar el aviso sin especificar la información de ubicación. El usuario podrá completar una llamada de emergencia, pero no podrá completarse ninguna otra llamada sin especificar la información. Además, puede mostrarse al usuario un texto de declinación de responsabilidades para alertarle sobre las consecuencias de negarse a especificar información de contacto. Para establecer el texto del aviso de declinación de responsabilidades, debe usar el shell de administración de Lync Server para ejecutar el cmdlet **set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener más información, vea [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) en la documentación del shell de administración de Lync Server.
            
            <div>
            

            > [!NOTE]  
            > En Lync Server 2013, puede usar la Directiva de ubicación para establecer diferentes declinaciones de responsabilidades para diferentes configuraciones regionales o conjuntos de usuarios distintos, a diferencia de lo que ocurre en Lync Server 2010, donde puede especificar solo una renuncia global para toda la organización.

            
            </div>
    
      - **Usar la ubicación solo**     para los servicios de emergencia Lync puede usar la información de ubicación por varios motivos (por ejemplo, para notificar a los compañeros de equipo de su ubicación actual). Seleccione esta casilla para garantizar que la información de ubicación solo está disponible para su uso en una llamada de emergencia.
    
      - **Uso**     de RTC Uso de la red telefónica conmutada (RTC) que se usará para determinar qué ruta de voz se usará para enrutar llamadas de emergencia de clientes que usen este perfil. La ruta asociada con este uso debe hacer referencia a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que desvíe las llamadas de emergencia al PSAP (Punto de respuesta de seguridad pública) más cercano.
    
      - Número de marcado de **emergencia**     El número que se marca para tener acceso a los servicios de emergencia. En los EE. UU. el número es 911. La cadena debe estar formada por dígitos del 0 al 9 y puede contener de uno a diez dígitos.
    
      - Máscara de marcado de **emergencia**     Un número que desea traducir en el valor del número de marcado de emergencia cuando se marca. Por ejemplo, si especifica el valor "212" en este campo y el número de teléfono de emergencia tiene el valor "911", cuando un usuario marca 212, la llamada se realizará al 911. Esto permite marcar números de emergencia alternativos y seguir teniendo acceso a los servicios de emergencia (por ejemplo, si una persona de un país o una región con otro número de emergencia intenta marcar el número de su país o región, en lugar del número del país o la región donde se encuentra.) Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. La longitud máxima de la cadena es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Compruebe que el valor de la máscara de marcado no coincide con ningún número del intervalo de la órbita de estacionamiento de llamadas. El enrutamiento del estacionamiento de llamadas tiene prioridad sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos existentes en la órbita de estacionamiento de llamadas, haga clic en  <STRONG>Características de voz</STRONG> en la barra de navegación izquierda y seleccione <STRONG>Estacionamiento de llamadas</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure Phone Number Extensions for estacionamiento calls in Lync Server 2013</A>.

        
        </div>
    
      - **URI**     de notificación Uno o más identificadores uniformes de recursos (URI) de SIP a los que se va a notificar cuando se realice una llamada de emergencia. Por ejemplo, el departamento de seguridad de la empresa puede recibir una notificación por mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, se incluirá dicha ubicación en la notificación. Se pueden incluir varios URI del SIP, separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". No se admiten listas de distribución. La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo "sip:". Antes de que haga clic en el campo URI de notificación aparecerá un ejemplo.
    
      - **URI**     de conferencia El URI del SIP, en este caso, el número de teléfono de un tercero que se unirá a las llamadas de emergencia realizadas. Por ejemplo, el departamento de seguridad de la empresa puede recibir una llamada cuando se realiza una llamada de emergencia y escuchar o participar en la conversación (según el valor proporcionado en el campo **Modo de conferencia**). La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo sip:. Aparece un ejemplo hasta que se hace clic dentro del campo.
    
      - **Modo**     de conferencia Si especifica un valor en el campo **URI de conferencia** , el **modo de conferencia** determina si un tercero puede participar en la llamada o solo puede escuchar. Especifique una de las opciones siguientes:
        
          - **Unidireccional**     Un tercero solo puede escuchar la conversación entre el autor de la llamada y el operador PSAP.
        
          - **Ambos sentidos**     Un tercero puede escuchar y participar en la llamada entre el autor de la llamada y el operador PSAP.

6.  Haga clic en **Confirmar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando crea una directiva de usuario, no se aplica inicialmente a ningún usuario o sitio de red. Para aplicar la directiva a un usuario, haga clic en <STRONG>Usuarios</STRONG> en la barra de navegación izquierda. Busque al usuario al que desea aplicarle la directiva. En el menú <STRONG>Editar</STRONG>, haga clic en <STRONG>Mostrar detalles</STRONG>. En la página <STRONG>Editar usuario de Lync Server</STRONG>, seleccione una nueva directiva de ubicación de la lista desplegable <STRONG>Directiva de ubicación</STRONG> y, a continuación, haga clic en <STRONG>Confirmar</STRONG>.<BR>Para aplicar la directiva a un sitio de red, haga clic en <STRONG>Configuración de red</STRONG> en la barra de navegación izquierda y seleccione <STRONG>Sitio</STRONG>. Busque el sitio de red al que desea aplicarle la directiva. En el menú <STRONG>Editar</STRONG>, haga clic en <STRONG>Mostrar detalles</STRONG>. En la página <STRONG>Editar sitio</STRONG>, seleccione una nueva directiva de ubicación de la lista desplegable <STRONG>Directiva de ubicación</STRONG> y, a continuación, haga clic en <STRONG>Confirmar</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Para modificar una directiva de ubicación en el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página  **Editar directiva de ubicación **, modifique los campos según sea necesario (para obtener más información, consulte el paso 5 de los procedimientos "Para crear una nueva directiva de ubicación" expuestos anteriormente en este tema).

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Eliminación de una directiva de ubicación en Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definición de la Directiva de ubicación para Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurar extensiones de números de teléfono para las llamadas de estacionamiento en Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

