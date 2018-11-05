---
title: Creación o modificación de una directiva de ubicación
TOCTitle: Creación o modificación de una directiva de ubicación
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49888890
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de una directiva de ubicación

 

_**Última modificación del tema:** 2012-11-01_

En Lync Server 2013, puede usar la directiva de ubicación para aplicar opciones de configuración relacionadas con las funciones de 9-1-1 mejorado (E9-1-1) y la configuración de ubicación para usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la directiva de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, el 911 en los EE. UU.), si se debe informar a la seguridad corporativa de forma automática y cómo se debe desviar la llamada.

Puede configurar las directivas de ubicación en el grupo **Configuración de red** de Panel de control de Lync Server 2013. Desde Panel de control de Lync Server, podrá ver, crear, modificar o eliminar directivas de ubicación. Use los procedimientos que se describen en esta sección para crear o modificar una directiva de ubicación. Para obtener detalles sobre la eliminación de directivas de ubicación, vea [Eliminación de una directiva de ubicación](lync-server-2013-deleting-a-location-policy.md).

En Lync Server 2013, puede invalidar el tiempo predeterminado que transcurre entre las solicitudes de actualización de ubicación de clientes procedentes del Servicio de información de ubicaciones. El valor predeterminado es de 4 horas. Utilice el cmdlet **Set-CsLocationPolicy** con el parámetro LocationRefreshInterval para invalidar el valor predeterminado.

## Para crear una nueva directiva de ubicación en Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , haga clic en **Nuevo** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, elija el sitio al que desea aplicar la directiva y haga clic en **Aceptar**. En la página **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Sitio**, y el campo **Nombre** contiene el nombre del sitio que ha elegido. No puede modificar ninguno de estos campos. Se aplicará automáticamente una directiva de sitio a todos los usuarios del sitio especificado y se invalidará la directiva global para dichos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Usuario**. No puede modificar este valor. En el campo **Nombre**, escriba el nombre que desea asignar a esta directiva. Las directivas de usuario no se aplican automáticamente a ningún usuario. Tras crear la directiva de usuario, debe otorgar automáticamente dicha directiva a los usuarios o los sitios de red a los que desea que se aplique.

5.  Rellene los campos restantes como se muestra a continuación:
    
      - **Habilitar servicios de emergencia mejorados**    Active esta casilla para que los usuarios asociados a esta directiva puedan usar el E9-1-1. Cuando se habiliten los servicios de emergencia, los cliente de Lync Server recuperan la información de ubicación del registro y la incluyen cuando se produce una llamada de emergencia.
    
      - **Ubicación**    Especifique uno de los valores siguientes:
        
          - **Requerido**   Se solicitará al usuario que especifique información de ubicación cuando el cliente se registre en una nueva ubicación. El usuario puede anular la solicitud sin especificar ninguna información. Si se especifica información, primero responderá a la llamada de emergencia el proveedor de servicios de emergencia para verificar la ubicación antes de enrutar la llamada al operador PSAP (Punto de respuesta de seguridad pública), o lo que es lo mismo, al operador del 911.
        
          - **No requerido** No se solicitará al usuario que especifique una ubicación. Al realizar una llamada sin información de ubicación, el proveedor de servicios de emergencia responderá a la llamada y solicitará que se especifique una ubicación.
        
          - **Declinación de responsabilidades**   Esta opción es equivalente a **Requerido** con una diferencia: el usuario no puede anular la solicitud de información sin introducir datos. El usuario podrá completar una llamada de emergencia, pero no podrá completarse ninguna otra llamada sin especificar la información. Además, puede mostrarse al usuario un texto de declinación de responsabilidades para alertarle sobre las consecuencias de negarse a especificar información de contacto. Para establecer el texto de declinación de responsabilidades, debe usar el Shell de administración de Lync Server para ejecutar el **Set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener más información, vea [Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy) en la documentación de Shell de administración de Lync Server.
            

            > [!NOTE]
            > A diferencia de en Lync Server 2010, donde solo se podía especificar una declinación de responsabilidades global para toda la organización, en Lync Server 2013, puede usar la directiva de ubicación para configurar diferentes declinaciones de responsabilidades para distintas configuraciones regionales o conjuntos de usuarios.

    
      - **Usar ubicación solo para servicios de emergencia**   Lync puede usar la información de ubicación por diversas razones (por ejemplo, para notificar al resto del equipo su ubicación actual). Seleccione esta casilla para garantizar que la información de ubicación solo está disponible para su uso en una llamada de emergencia.
    
      - **Uso de RTC** Uso que se hará de la red telefónica conmutada (RTC) para averiguar qué ruta de voz se usa para enrutar llamadas de emergencia realizadas desde clientes que usen este perfil. La ruta asociada con este uso debe hacer referencia a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que desvíe las llamadas de emergencia al PSAP (Punto de respuesta de seguridad pública) más cercano.
    
      - **Número de teléfono de emergencia**   El número que se marca para tener acceso a los servicios de emergencia. En los EE. UU. el número es 911. La cadena debe estar formada por dígitos del 0 al 9 y puede contener de uno a diez dígitos.
    
      - **Máscara de marcado de emergencia**   Un número que al marcarlo se convertirá en el valor del número de teléfono de emergencia. Por ejemplo, si especifica el valor "212" en este campo y el número de teléfono de emergencia tiene el valor "911", cuando un usuario marca 212, la llamada se realizará al 911. Esto permite marcar números de emergencia alternativos y seguir teniendo acceso a los servicios de emergencia (por ejemplo, si una persona de un país o una región con otro número de emergencia intenta marcar el número de su país o región, en lugar del número del país o la región donde se encuentra.) Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. La longitud máxima de la cadena es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
        
        > [!IMPORTANT]  
        > Compruebe que el valor de la máscara de marcado no coincide con ningún número del intervalo de la órbita de estacionamiento de llamadas. El enrutamiento del estacionamiento de llamadas tiene prioridad sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos existentes en la órbita de estacionamiento de llamadas, haga clic en <strong>Características de voz</strong> en la barra de navegación izquierda y seleccione <strong>Estacionamiento de llamadas</strong>. Para obtener más información, consulte <a href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configurar extensiones de números de teléfono para estacionar llamadas</a>.
        
    
      - **URI de notificación** Uno o más identificadores uniformes de recursos (URI) del SIP que se notificarán al realizar una llamada de emergencia. Por ejemplo, el departamento de seguridad de la empresa puede recibir una notificación por mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, se incluirá dicha ubicación en la notificación. Se pueden incluir varios URI del SIP, separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". No se admiten listas de distribución. La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo "sip:". Antes de que haga clic en el campo URI de notificación aparecerá un ejemplo.
    
      - **URI de conferencia**   El URI del SIP, en este caso el número de teléfono, de un tercero que entrará en conferencia en cualquier llamada de emergencia realizada. Por ejemplo, el departamento de seguridad de la empresa puede recibir una llamada cuando se realiza una llamada de emergencia y escuchar o participar en la conversación (según el valor proporcionado en el campo **Modo de conferencia**). La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo sip:. Aparece un ejemplo hasta que se hace clic dentro del campo.
    
      - **Modo de conferencia**    Si especifica un valor en el campo **URI de conferencia** , el **Modo de conferencia** determina si puede participar un tercero en la llamada o si solo puede escucharla. Especifique una de las opciones siguientes:
        
          - **Unidireccional**    El tercero solo puede escuchar la conversación entre el autor de la llamada y el operador del servicio de emergencia.
        
          - **Bidireccional**    El tercero puede escuchar y participar en la conversación entre el autor de la llamada y el operador del servicio de emergencia.

6.  Haga clic en **Confirmar**.
    
    > [!IMPORTANT]  
    > Cuando crea una directiva de usuario, no se aplica inicialmente a ningún usuario o sitio de red. Para aplicar la directiva a un usuario, haga clic en <strong>Usuarios</strong> en la barra de navegación izquierda. Busque al usuario al que desea aplicarle la directiva. En el menú <strong>Editar</strong>, haga clic en <strong>Mostrar detalles</strong>. En la página <strong>Editar usuario de Lync Server</strong>, seleccione una nueva directiva de ubicación de la lista desplegable <strong>Directiva de ubicación</strong> y, a continuación, haga clic en <strong>Confirmar</strong>.<br />
    > Para aplicar la directiva a un sitio de red, haga clic en <strong>Configuración de red</strong> en la barra de navegación izquierda y seleccione <strong>Sitio</strong>. Busque el sitio de red al que desea aplicarle la directiva. En el menú <strong>Editar</strong>, haga clic en <strong>Mostrar detalles</strong>. En la página <strong>Editar sitio</strong>, seleccione una nueva directiva de ubicación de la lista desplegable <strong>Directiva de ubicación</strong> y, a continuación, haga clic en <strong>Confirmar</strong>.


## Para modificar una directiva de ubicación en Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar directiva de ubicación** , modifique los campos según sea necesario (para obtener más información, consulte el paso 5 de los procedimientos "Para crear una nueva directiva de ubicación" expuestos anteriormente en este tema).

7.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Eliminación de una directiva de ubicación](lync-server-2013-deleting-a-location-policy.md)  

#### Conceptos

[Definir una directiva de ubicación para Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  

#### Otros recursos

[Configurar extensiones de números de teléfono para estacionar llamadas](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

