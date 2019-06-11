---
title: 'Lync Server 2013: crear o modificar una directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173cfd6ce158a089e03a9eded12c3c6920183463
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Crear o modificar una directiva de ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada de 9-1-1 (E9-1-1) y la configuración de ubicación de los usuarios o los contactos. La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo debe dirigirse la llamada.

Puede configurar directivas de ubicación desde el grupo **configuración de red** en el panel de control de Lync Server 2013. En el panel de control de Lync Server puede ver, crear, modificar o eliminar directivas de ubicación. Use los procedimientos de esta sección para crear o modificar una directiva de ubicación. Para obtener más información sobre cómo eliminar directivas de ubicación, consulte [eliminar una directiva de ubicación en Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

En Lync Server 2013, puede invalidar la cantidad de tiempo predeterminada entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor predeterminado es de 4 horas. Use el cmdlet **set-CsLocationPolicy** con el parámetro LocationRefreshInterval para invalidar el valor predeterminado.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Para crear una nueva Directiva de ubicación en el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , haga clic en **nuevo** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, elija el sitio al que desea aplicar la Directiva y haga clic en **Aceptar**. En la página **nueva Directiva de ubicación** , el campo **ámbito** contiene el valor **sitio**y el campo **nombre** contiene el nombre del sitio que ha elegido. No puede modificar ninguno de estos campos. Una directiva de sitio se aplica automáticamente a todos los usuarios del sitio especificado y reemplaza la directiva global para esos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En la **nueva Directiva de ubicación**, el campo **ámbito** contiene el valor **usuario**. Este valor no se puede modificar. En el campo **nombre** , escriba el nombre que desea asignar a esta Directiva. Una directiva de usuario no se aplica automáticamente a ningún usuario. Después de crear la Directiva de usuario, debe conceder manualmente la Directiva a los usuarios o sitios de red a los que desea aplicar la Directiva.

5.  Rellene los campos restantes de la siguiente manera:
    
      - **Habilitar servicios**   de emergencia mejorados Active esta casilla para habilitar los usuarios asociados a esta directiva para E9-1-1. Cuando los servicios de emergencia están habilitados, los clientes de Lync Server recuperarán información sobre la ubicación en el registro y la incluirán cuando se realice una llamada de emergencia.
    
      - **Ubicación**   especifique uno de los siguientes valores:
        
          - **Requerido**   se le solicitará al usuario que escriba la información de ubicación cuando el cliente se registre en una nueva ubicación. El usuario puede descartar la pregunta sin escribir ninguna información. Si se introduce información, el proveedor de servicios de emergencias contestará primero a una llamada de emergencia para verificar la ubicación antes de enrutarse al operador del punto de respuesta de seguridad (PSAP) (es decir, el operador de 911).
        
          - **No se requiere**   que se solicite al usuario una ubicación. Cuando se realiza una llamada sin información de la ubicación, el proveedor de servicios de emergencias responderá a la llamada y pedirá una ubicación.
        
          - **Renuncia**   esta opción es la misma que la **requerida** , excepto que el usuario no puede descartar la pregunta sin especificar la información de la ubicación. El usuario aún puede completar una llamada de emergencia, pero no se puede completar ninguna otra llamada sin introducir la información. Además, se mostrará el texto de renuncia al usuario que puede alertarles de las consecuencias de la declinación de la información de la ubicación. Para establecer el texto de renuncia, debe usar el shell de administración de Lync Server para ejecutar el cmdlet **set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener más información, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) en la documentación del shell de administración de Lync Server.
            
            <div>
            

            > [!NOTE]  
            > En Lync Server 2013, puede usar la Directiva de ubicación para establecer diferentes renuncias para diferentes configuraciones regionales o conjuntos de usuarios diferentes, a diferencia de Lync Server 2010, donde puede especificar solo un aviso de declinación de responsabilidades global para toda la organización.

            
            </div>
    
      - **Usar ubicación para servicios de emergencia solo**   Lync puede usar la información de la ubicación por varios motivos (por ejemplo, para notificar a los compañeros de equipo de su ubicación actual). Seleccione esta casilla para asegurarse de que la información de ubicación solo esté disponible para su uso con una llamada de emergencia.
    
      - **Uso de RTC**   el uso de la red de telefonía pública conmutada (RTC) que se usará para determinar qué ruta de voz se usará para enrutar llamadas de emergencia de clientes que usen este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano.
    
      - **Número de marcado de emergencia**   número que se marca para llegar a servicios de emergencia. En Estados Unidos, este valor es 911. La cadena debe estar formada por los dígitos del 0 al 9 y puede tener entre 1 y 10 dígitos de longitud.
    
      - **Máscara de marcado de emergencia**   número que desea traducir en el valor del valor de número de marca de emergencia cuando se marca. Por ejemplo, si escribe un valor de 212 en este campo y el campo número de marca de emergencia tiene un valor de 911, si un usuario marca 212, la llamada se realizará en 911. Esto permite que se marquen números de emergencia alternativos y siga haciendo que las llamadas lleguen a servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número de la país o región en el que se encuentran actualmente). Puede definir varias máscaras de marcado de emergencia si separa los valores con signos de punto y coma. Por ejemplo, 212; 414. La longitud máxima de la cadena es de 100 caracteres. Cada carácter debe ser un dígito del 0 al 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Asegúrese de que el valor de máscara de marcado especificada no es el mismo que un número de un intervalo de llamada en órbita. El enrutamiento de estacionamiento de llamadas tendrá prioridad sobre la conversión de cadenas de marcación de emergencia. Para ver los intervalos de la órbita de estacionamiento de llamadas existentes, haga clic en <STRONG>características de voz</STRONG> en la barra de navegación izquierda y luego en <STRONG>llamar a estacionamiento</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">configurar extensiones de números de teléfono para llamadas de aparcamiento en Lync Server 2013</A>.

        
        </div>
    
      - **URI de notificación**   : uno o más identificadores uniformes de recursos (URI) SIP que recibirán una notificación cuando se realice una llamada de emergencia. Por ejemplo, se puede notificar a la oficina de seguridad de la empresa a través de un mensaje instantáneo siempre que se hace una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, esa ubicación se incluirá en la notificación. Los URI de varios SIP se pueden incluir como una lista separada por comas. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Se admiten las listas de distribución. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". Antes de hacer clic en el campo URI de notificación se muestra un ejemplo.
    
      - **Uri**   de la Conferencia el URI del SIP, en este caso, el número de teléfono de un tercero que se pondrá en conferencia con cualquier llamada de emergencia que se realice. Por ejemplo, la oficina de seguridad de la empresa podría recibir una llamada cuando se realiza una llamada de emergencia y escuchar o participar en la llamada (según el valor suministrado en el campo **modo de conferencia** ). La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:. Se muestra un ejemplo hasta que hace clic dentro de este campo.
    
      - **Modo**   de conferencia si especifica un valor en el campo URI de la **Conferencia** , el **modo de conferencia** determina si un tercero puede participar en la llamada o si solo puede escuchar. Especifique una de las siguientes opciones:
        
          - **** Una tercera persona sólo puede escuchar la conversación entre el autor de la llamada y el operador PSAP.   
        
          - **Dos direcciones**   de terceros pueden escuchar y participar en la llamada entre el operador de llamadas y el operador PSAP.

6.  Haga clic en **Confirmar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Al crear una directiva de usuario, inicialmente esa Directiva no se aplica a ninguno de los usuarios o sitios de red. Para aplicar la Directiva a un usuario, haga clic en <STRONG>usuarios</STRONG> en la barra de navegación izquierda. Busque el usuario al que desea aplicar la Directiva. En el menú <STRONG>Editar</STRONG>, haga clic en <STRONG>Mostrar detalles</STRONG>. En la página <STRONG>Editar usuario de Lync Server</STRONG> , seleccione la nueva Directiva de ubicación en la lista desplegable <STRONG>Directiva de ubicación</STRONG> y, a continuación, haga clic en <STRONG>confirmar</STRONG>.<BR>Para aplicar la Directiva a un sitio de red, haga clic en <STRONG>configuración de red</STRONG> en la barra de navegación izquierda y, después, haga clic en <STRONG>sitio</STRONG>. Busque el sitio de red al que desea aplicar la Directiva. En el menú <STRONG>Editar</STRONG>, haga clic en <STRONG>Mostrar detalles</STRONG>. En <STRONG>Editar sitio</STRONG>, seleccione la nueva Directiva de ubicación en la lista desplegable <STRONG>Directiva de ubicación</STRONG> y, a continuación, haga clic en <STRONG>confirmar</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Para modificar una directiva de ubicación en el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar Directiva de ubicación** , modifique los campos según sea necesario (para obtener información detallada, consulte el paso 5 de los procedimientos "para crear una nueva Directiva de ubicación" anteriormente en este tema).

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar una directiva de ubicación en Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurar extensiones de números de teléfono para llamadas de aparcamiento en Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

