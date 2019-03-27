---
title: Administración de 9-1-1 mejorado y el servicio de ubicación
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server es compatible con Enhanced 9-1-1 (E9-1-1) de llamada de Skype para clientes empresariales. Al configurar Skype para Business Server para E9-1-1, las llamadas de emergencias realizadas desde Skype para la empresa incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos de servicio de información de ubicación.
ms.openlocfilehash: 31e1d529c8fb60145bc1ab4a22a75660d9f3ef63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895156"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Administración de 9-1-1 mejorado y el servicio de ubicación en Skype para Business Server

Skype para Business Server es compatible con Enhanced 9-1-1 (E9-1-1) de llamada de Skype para clientes empresariales. Al configurar Skype para Business Server para E9-1-1, las llamadas de emergencias realizadas desde Skype para la empresa incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos de servicio de información de ubicación. Use los procedimientos de este artículo para administrar la directiva de ubicación.

> [!Note]
> Para obtener información detallada sobre la implementación de características avanzadas de Enterprise Voice, como E9-1-1 y el servicio de información de ubicación, vea [implementar Enterprise Voice características avanzadas](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

En Skype para Business Server, puede usar la directiva de ubicación para aplicar la configuración que se relacionan con a la funcionalidad de 9-1-1 mejorado (E9-1-1) y a la configuración de ubicación para los usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, ¿qué es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la directiva de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los Estados Unidos), si se debe notificar automáticamente seguridad corporativa y cómo se debe enrutar la llamada.

Puede configurar las directivas de ubicación desde el grupo de **Configuración de red** en el Skype para el Panel de Control de servidor empresarial. Desde el Skype para el Panel de Control de servidor empresarial puede ver, crear, modificar o eliminar las directivas de ubicación. Use el procedimiento siguiente para ver información sobre las directivas de ubicación. 


## <a name="view-location-policy-information"></a>Ver información de directivas de ubicación 

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.
 
    > [!NOTE]  
    > Sólo se puede ver información acerca de la directiva de una ubicación a la vez.

Una directiva única, denominada Global, existe de forma predeterminada y no pueden eliminarse ni cambiar el nombre. Sin embargo, puede modificar la directiva Global. Esta directiva se aplicará a todos los usuarios y contactos, a menos que cree las directivas de sitio o por usuario. Directivas por usuario se deben aplicar a usuarios específicos.


## <a name="create-or-modify-a-location-policy"></a>Crear o modificar una directiva de ubicación 

En Skype para Business Server, se puede invalidar la cantidad de tiempo entre las solicitudes de cliente para una actualización de la ubicación del servicio de información de la ubicación predeterminada. El valor predeterminado es de 4 horas. Use el cmdlet **Set-CsLocationPolicy** con el parámetro LocationRefreshInterval para reemplazar el valor predeterminado.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para crear una nueva directiva de ubicación en la Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , haga clic en **nuevo** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, elija el sitio al que desea que la directiva aplicada y haga clic en **Aceptar**. En la página **Nueva directiva de ubicación** , el campo de **ámbito** contiene el valor del **sitio**y el campo **nombre** contiene el nombre del sitio que ha elegido. No se puede modificar cualquiera de estos campos. Una directiva de sitio se aplica automáticamente a todos los usuarios en el sitio especificado y reemplaza la directiva global para esos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En la **Nueva directiva de ubicación**, el campo de **ámbito** contiene el valor de **usuario**. No se puede modificar este valor. En el campo **nombre** , escriba el nombre que desea dar a esta directiva. Una directiva de usuario no se aplica automáticamente a todos los usuarios. Después de crear la directiva de usuario, debe conceder manualmente la directiva a los usuarios o sitios de red que desea para la directiva que se debe aplicar.

5.  Rellene los campos restantes de la siguiente manera:
    
      - **Habilitar mejorada de los servicios de emergencia**   Active esta casilla de verificación para habilitar los usuarios asociados con esta directiva para E9-1-1. Cuando se habilitan los servicios de emergencia, Skype para los clientes de Business Server va a recuperar la información de ubicación en el registro e incluir esa información cuando se realiza una llamada de emergencia.
    
      - **Ubicación de**   especificar uno de los siguientes valores:
        
          - **Requiere**   le pedirá al usuario a la información de ubicación de entrada cuando el cliente se registra en una nueva ubicación. El usuario puede cerrar el símbolo del sistema sin introducir ningún dato. Si se escribe información, una llamada de emergencia en primer lugar se ha atendido por el proveedor de servicios de emergencia para comprobar la ubicación antes de que se enrutan al operador de punto de respuesta de seguridad pública (PSAP) (es decir, el 911 operador).
        
          - **No es necesario**   el usuario no se le pida una ubicación. Cuando se realiza una llamada sin información de ubicación, el proveedor de servicios de emergencia responda a la llamada y solicitar una ubicación.
        
          - **Declinación de responsabilidades**   esta opción es igual a **necesarios** , excepto en que el usuario no puede cerrar el símbolo del sistema sin tener que especificar información de ubicación. El usuario aún puede completar una llamada de emergencia, pero no hay otras llamadas pueden completarse sin necesidad de especificar la información. Además, el texto de declinación de responsabilidades se mostrará al usuario que puede avisarle de que a las consecuencias de disminución escribir información de ubicación. Para establecer el texto de declinación de responsabilidades, debe usar el Skype para Business Server Management Shell para ejecutar el cmdlet **Set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener información detallada, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Ubicación de uso para servicios de emergencia sólo** Skype para la empresa puede usar la información de ubicación por varias razones (por ejemplo, para notificar a los compañeros de equipo de su ubicación actual). Active esta casilla de verificación para garantizar la información de ubicación sólo está disponible para su uso con una llamada de emergencia.
    
      - **Uso de RTC**   conmutada telefónicos de red (RTC) que se usará para determinar qué ruta de voz se usará para enrutar las llamadas de emergencia desde clientes que usen este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano.
    
      - **Número de marcado de emergencia**   el número que se marca para llegar a los servicios de emergencia. En los Estados Unidos, este valor es 911. La cadena debe estar formada por dígitos del 0 al 9 y puede contener de 1 a 10 dígitos de longitud.
    
      - **Máscara de marcado de emergencia**   un número que se va a traducir en el valor del valor del número marcado de emergencia cuando se marca. Por ejemplo, si se escribe un valor de 212 en este campo y el campo número de marcado de emergencia tiene un valor de 911, si un usuario marca 212 se realizará la llamada al 911. Esto permite que los números de emergencias alternativos se debe marcar y seguir teniendo la llamada llegar a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número diferente de emergencia intenta marcar que país o región del número en vez del número de la país o región que se encuentran actualmente en). Puede definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212; 414. Longitud máxima de la cadena es de 100 caracteres. Cada carácter debe ser un dígito de 0 a 9.
      

        > [!IMPORTANT]  
        > Asegúrese de que el valor de máscara de marcado especificado no es el mismo que el número en un intervalo de órbitas de estacionamiento de llamadas. Enrutamiento de estacionamiento de llamadas tienen prioridad sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos de Órbitas del estacionamiento de llamadas, haga clic en **Características de voz** en la barra de navegación izquierdo y, a continuación, haga clic en **Estacionamiento de llamadas**. 

    
      - **URI de notificación**   uno o más SIP identificadores uniformes de recursos (URI) para recibir una notificación cuando se realiza una llamada de emergencia. Por ejemplo, la oficina de seguridad de la compañía puede recibir una notificación a través de un mensaje instantáneo siempre que se realiza una llamada de emergencia. Si ubicación el autor de la llamada está disponible, esa ubicación se incluirá en la notificación. Varios identificadores URI de SIP pueden incluir como una lista separada por comas. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Se admiten las listas de distribución. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". Antes de hacer clic en el campo URI de notificación se muestra un ejemplo.
    
      - **URI de conferencia**   el URI de SIP, en este caso, el número de teléfono, de un tercero que será incluirse en la conferencia a las llamadas de emergencias que se realizan. Por ejemplo, la oficina de seguridad de la compañía pudo recibe una llamada cuando se realiza una llamada de emergencia y escuchar o participar en esa llamada (según el valor proporcionado en el campo de **modo de conferencia** ). La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:. Hasta que haga clic dentro de este campo, se muestra un ejemplo.
    
      - **Modo de conferencia**   si especifica un valor en el campo **URI de conferencia** , el **modo de conferencia** determina si un tercero puede participar en la llamada o solo puede escuchar. Especifique una de las siguientes opciones:
        
          - **One-Way**   un tercero sólo puede escuchar la conversación entre el autor de la llamada y el operador del servicio de emergencia.
        
          - **Bidireccional**   un tercero puede escuchar y participar en la llamada entre el autor de la llamada y el operador del servicio de emergencia.

6.  Haga clic en **Confirmar**.


    > [!IMPORTANT]  
    > Cuando se crea una directiva de usuario, inicialmente esa directiva no se aplica a los usuarios o sitios de red. Para aplicar la directiva a un usuario, haga clic en **usuarios** , en la barra de navegación izquierda. Busque el usuario al que desea aplicar la directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En la página **Editar usuario de servidor** , seleccione la nueva directiva de ubicación de la lista desplegable **Directiva de ubicación** y, a continuación, haga clic en **Confirmar**.<BR>Para aplicar la directiva a un sitio de red, haga clic en **Configuración de red** en la barra de navegación izquierdo y, a continuación, haga clic en **sitio**. Busque el sitio de red a la que desea aplicar la directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En **Modificar sitio**, seleccione la nueva directiva de ubicación de la lista desplegable **Directiva de ubicación** y, a continuación, haga clic en **Confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar una directiva de ubicación en la Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar directiva de ubicación** , modifique los campos según sea necesario (para obtener información detallada, consulte el paso 5 de la "para crear una nueva directiva de ubicación" procedimientos anteriormente en este tema).

7.  Haga clic en **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Eliminar una directiva de ubicación


1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la directiva de ubicación que desea eliminar.
   
    > [!NOTE]  
    > Puede eliminar más de una directiva de ubicación a la vez. Para ello, presione la tecla CTRL y seleccione varias directivas mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en **Seleccionar todo** en el menú **Edición** .


5.  En el menú **Edición** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

    > [!IMPORTANT]  
    > No se puede eliminar la directiva de ubicación Global. Si se intenta eliminar la directiva Global, recibirá un mensaje de advertencia y esa directiva se restablecerán a sus valores predeterminados.


## <a name="see-also"></a>Consulte también

[Crear o modificar sitios de red](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[Nueva CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
