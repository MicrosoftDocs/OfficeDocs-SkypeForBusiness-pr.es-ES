---
title: Administrar la 9-1-1 mejorada y el servicio de ubicación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype empresarial Server admite llamadas mejoradas de 9-1-1 (E9-1-1) desde clientes de Skype empresarial. Al configurar Skype empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype empresarial incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación.
ms.openlocfilehash: de02c4a9a3210220e368d87d4ae8e21a80f3dbac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818431"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Administrar la 9-1-1 mejorada y el servicio de ubicación en Skype para Business Server

Skype empresarial Server admite llamadas mejoradas de 9-1-1 (E9-1-1) desde clientes de Skype empresarial. Al configurar Skype empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype empresarial incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Use los procedimientos de este artículo para administrar la Directiva de ubicación.

> [!Note]
> Para obtener más información sobre las características avanzadas de la telefonía IP empresarial, como E9-1-1 y el servicio de información de ubicación, consulte [implementar características avanzadas de voz empresarial](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

En Skype empresarial Server, puede usar la Directiva ubicación para aplicar la configuración relacionada con la funcionalidad mejorada de 9-1-1 (E9-1-1) y la configuración de ubicación de los usuarios o los contactos. La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo debe dirigirse la llamada.

Puede configurar directivas de ubicación desde el grupo **configuración de red** en el panel de control de Skype empresarial Server. En el panel de control de Skype empresarial Server puede ver, crear, modificar o eliminar directivas de ubicación. Use el procedimiento siguiente para ver información sobre las directivas de ubicación. 


## <a name="view-location-policy-information"></a>Ver información de directiva de ubicación 

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.
 
    > [!NOTE]  
    > Solo puede ver información sobre una política de ubicación a la vez.

De forma predeterminada, existe una única directiva, denominada global, que no se puede eliminar ni cambiar de nombre. Sin embargo, puede modificar la directiva global. Esta Directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario. Las directivas por usuario deben aplicarse a usuarios específicos.


## <a name="create-or-modify-a-location-policy"></a>Crear o modificar una directiva de ubicación 

En Skype empresarial Server, puede invalidar la cantidad de tiempo predeterminada entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor predeterminado es de 4 horas. Use el cmdlet **set-CsLocationPolicy** con el parámetro LocationRefreshInterval para invalidar el valor predeterminado.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para crear una nueva Directiva de ubicación en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , haga clic en **nuevo** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, elija el sitio al que desea aplicar la Directiva y haga clic en **Aceptar**. En la página **nueva Directiva de ubicación** , el campo **ámbito** contiene el valor **sitio**y el campo **nombre** contiene el nombre del sitio que ha elegido. No puede modificar ninguno de estos campos. Una directiva de sitio se aplica automáticamente a todos los usuarios del sitio especificado y reemplaza la directiva global para esos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En la **nueva Directiva de ubicación**, el campo **ámbito** contiene el valor **usuario**. Este valor no se puede modificar. En el campo **nombre** , escriba el nombre que desea asignar a esta Directiva. Una directiva de usuario no se aplica automáticamente a ningún usuario. Después de crear la Directiva de usuario, debe conceder manualmente la Directiva a los usuarios o sitios de red a los que desea aplicar la Directiva.

5.  Rellene los campos restantes de la siguiente manera:
    
      - **Habilitar servicios**   de emergencia mejorados Active esta casilla para habilitar los usuarios asociados a esta directiva para E9-1-1. Cuando se habilitan los servicios de emergencia, los clientes de Skype empresarial Server recuperarán la información sobre la ubicación del registro y la incluirán cuando se realice una llamada de emergencia.
    
      - **Ubicación**   especifique uno de los siguientes valores:
        
          - **Requerido**   se le solicitará al usuario que escriba la información de ubicación cuando el cliente se registre en una nueva ubicación. El usuario puede descartar la pregunta sin escribir ninguna información. Si se introduce información, el proveedor de servicios de emergencias contestará primero a una llamada de emergencia para verificar la ubicación antes de enrutarse al operador del punto de respuesta de seguridad (PSAP) (es decir, el operador de 911).
        
          - **No se requiere**   que se solicite al usuario una ubicación. Cuando se realiza una llamada sin información de la ubicación, el proveedor de servicios de emergencias responderá a la llamada y pedirá una ubicación.
        
          - **Renuncia**   esta opción es la misma que la **requerida** , excepto que el usuario no puede descartar la pregunta sin especificar la información de la ubicación. El usuario aún puede completar una llamada de emergencia, pero no se puede completar ninguna otra llamada sin introducir la información. Además, se mostrará el texto de renuncia al usuario que puede alertarles de las consecuencias de la declinación de la información de la ubicación. Para establecer el texto de renuncia, debe usar el shell de administración de Skype empresarial Server para ejecutar el cmdlet **set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener más información, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Usar la ubicación solo para servicios de emergencia** Skype empresarial puede usar la información de ubicación por diversos motivos (por ejemplo, para notificar a los compañeros de equipo de su ubicación actual). Seleccione esta casilla para asegurarse de que la información de ubicación solo esté disponible para su uso con una llamada de emergencia.
    
      - **Uso de RTC**   el uso de la red de telefonía pública conmutada (RTC) que se usará para determinar qué ruta de voz se usará para enrutar llamadas de emergencia de clientes que usen este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano.
    
      - **Número de marcado de emergencia**   número que se marca para llegar a servicios de emergencia. En Estados Unidos, este valor es 911. La cadena debe estar formada por los dígitos del 0 al 9 y puede tener entre 1 y 10 dígitos de longitud.
    
      - **Máscara de marcado de emergencia**   número que desea traducir en el valor del valor de número de marca de emergencia cuando se marca. Por ejemplo, si escribe un valor de 212 en este campo y el campo número de marca de emergencia tiene un valor de 911, si un usuario marca 212, la llamada se realizará en 911. Esto permite que se marquen números de emergencia alternativos y siga haciendo que las llamadas lleguen a servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número de la país o región en el que se encuentran actualmente). Puede definir varias máscaras de marcado de emergencia si separa los valores con signos de punto y coma. Por ejemplo, 212; 414. La longitud máxima de la cadena es de 100 caracteres. Cada carácter debe ser un dígito del 0 al 9.
      

        > [!IMPORTANT]  
        > Asegúrese de que el valor de máscara de marcado especificada no es el mismo que un número de un intervalo de llamada en órbita. El enrutamiento de estacionamiento de llamadas tendrá prioridad sobre la conversión de cadenas de marcación de emergencia. Para ver los intervalos de la órbita de estacionamiento de llamadas existentes, haga clic en **características de voz** en la barra de navegación izquierda y luego en **llamar a estacionamiento**. 

    
      - **URI de notificación**   : uno o más identificadores uniformes de recursos (URI) SIP que recibirán una notificación cuando se realice una llamada de emergencia. Por ejemplo, se puede notificar a la oficina de seguridad de la empresa a través de un mensaje instantáneo siempre que se hace una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, esa ubicación se incluirá en la notificación. Los URI de varios SIP se pueden incluir como una lista separada por comas. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Se admiten las listas de distribución. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". Antes de hacer clic en el campo URI de notificación se muestra un ejemplo.
    
      - **Uri**   de la Conferencia el URI del SIP, en este caso, el número de teléfono de un tercero que se pondrá en conferencia con cualquier llamada de emergencia que se realice. Por ejemplo, la oficina de seguridad de la empresa podría recibir una llamada cuando se realiza una llamada de emergencia y escuchar o participar en la llamada (según el valor suministrado en el campo **modo de conferencia** ). La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:. Se muestra un ejemplo hasta que hace clic dentro de este campo.
    
      - **Modo**   de conferencia si especifica un valor en el campo URI de la **Conferencia** , el **modo de conferencia** determina si un tercero puede participar en la llamada o si solo puede escuchar. Especifique una de las siguientes opciones:
        
          - **Una tercera**persona sólo puede escuchar la conversación entre el autor de la llamada y el operador PSAP.   
        
          - **Dos direcciones**   de terceros pueden escuchar y participar en la llamada entre el operador de llamadas y el operador PSAP.

6.  Haga clic en **Confirmar**.


    > [!IMPORTANT]  
    > Al crear una directiva de usuario, inicialmente esa Directiva no se aplica a ninguno de los usuarios o sitios de red. Para aplicar la Directiva a un usuario, haga clic en **usuarios** en la barra de navegación izquierda. Busque el usuario al que desea aplicar la Directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En la página **Editar usuario del servidor** , seleccione la nueva Directiva de ubicación en la lista desplegable **Directiva de ubicación** y, a continuación, haga clic en **confirmar**.<BR>Para aplicar la Directiva a un sitio de red, haga clic en **configuración de red** en la barra de navegación izquierda y, después, haga clic en **sitio**. Busque el sitio de red al que desea aplicar la Directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En **Editar sitio**, seleccione la nueva Directiva de ubicación en la lista desplegable **Directiva de ubicación** y, a continuación, haga clic en **confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar una directiva de ubicación en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar Directiva de ubicación** , modifique los campos según sea necesario (para obtener información detallada, consulte el paso 5 de los procedimientos "para crear una nueva Directiva de ubicación" anteriormente en este tema).

7.  Haga clic en **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Eliminar una directiva de ubicación


1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea eliminar.
   
    > [!NOTE]  
    > Puede eliminar más de una política de ubicación a la vez. Para ello, presione CTRL y seleccione varias directivas mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en **seleccionar todo** en el menú **edición** .


5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.

    > [!IMPORTANT]  
    > No se puede eliminar la Directiva de ubicación global. Si intenta eliminar la directiva global, recibirá un mensaje de advertencia y esa Directiva se restablecerá a sus valores predeterminados.


## <a name="see-also"></a>Vea también

[Crear o modificar sitios de red](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[Nuevo: CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
