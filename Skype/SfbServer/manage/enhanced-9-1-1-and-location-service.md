---
title: Administrar 9-1-1 mejorado y el servicio de ubicación
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Empresarial Server admite llamadas mejoradas 9-1-1 (E9-1-1) desde Skype Empresarial cliente. Al configurar Skype Empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype Empresarial incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación.
ms.openlocfilehash: cff19de879066163f53de6b8d51ef8384d451438
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763778"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Administrar 9-1-1 mejorado y el servicio de ubicación en Skype busines server

Skype Empresarial Server admite llamadas mejoradas 9-1-1 (E9-1-1) desde Skype Empresarial cliente. Al configurar Skype Empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype Empresarial incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Use los procedimientos de este artículo para administrar la directiva de ubicación.

> [!Note]
> Para obtener información detallada sobre cómo implementar características Telefonía IP empresarial avanzadas, como E9-1-1 y el servicio de información de ubicación, vea [Deploy advanced Telefonía IP empresarial features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

En Skype Empresarial Server, puede usar la directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación para usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la directiva de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.

Puede configurar directivas de ubicación desde el grupo **Configuración de** red en el panel Skype Empresarial Server control. Desde el panel Skype Empresarial Server control puede ver, crear, modificar o eliminar directivas de ubicación. Use el siguiente procedimiento para ver información sobre las directivas de ubicación. 


## <a name="view-location-policy-information"></a>Ver información de directiva de ubicación 

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva **de ubicación.**

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.
 
    > [!NOTE]  
    > Solo puede ver información sobre una directiva de ubicación a la vez.

Una única directiva, denominada Global, existe de forma predeterminada y no se puede eliminar ni cambiar el nombre. Sin embargo, puede modificar la directiva global. Esta directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario. Las directivas por usuario deben aplicarse a usuarios específicos.


## <a name="create-or-modify-a-location-policy"></a>Crear o modificar una directiva de ubicación 

En Skype Empresarial Server, puede invalidar la cantidad de tiempo predeterminada entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor predeterminado es 4 horas. Utilice el cmdlet **Set-CsLocationPolicy** con el parámetro LocationRefreshInterval para invalidar el valor predeterminado.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para crear una nueva directiva de ubicación en el Panel Skype Empresarial Server control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva **de ubicación.**

4.  En la página  **Directiva de ubicación**, haga clic en  **Nuevo** y, a continuación, seleccione el tipo de directiva que desea crear:
    
      - Para crear una directiva de sitio, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, elija el sitio al que desea aplicar la directiva y haga clic en **Aceptar**. En la página **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Sitio**, y el campo **Nombre** contiene el nombre del sitio que ha elegido. No puede modificar ninguno de estos campos. Se aplicará automáticamente una directiva de sitio a todos los usuarios del sitio especificado y se invalidará la directiva global para dichos usuarios.
    
      - Para crear una **Directiva de usuario**, haga clic en **Directiva de usuario**. En **Nueva directiva de ubicación**, el campo **Ámbito** contiene el valor **Usuario**. No puede modificar este valor. En el campo **Nombre**, escriba el nombre que desea asignar a esta directiva. Las directivas de usuario no se aplican automáticamente a ningún usuario. Tras crear la directiva de usuario, debe otorgar automáticamente dicha directiva a los usuarios o los sitios de red a los que desea que se aplique.

5.  Rellene los campos restantes como se muestra a continuación:
    
      - **Habilitar servicios de emergencia mejorados**   Active esta casilla para habilitar los usuarios asociados con esta directiva para E9-1-1. Cuando los servicios de emergencia están habilitados, Skype Empresarial Server los clientes recuperarán la información de ubicación en el registro e incluirán esa información cuando se realiza una llamada de emergencia.
    
      - **Ubicación**   Especifique uno de los valores siguientes:
        
          - **Requerido**   Se solicitará al usuario que especifique información de ubicación cuando el cliente se registre en una nueva ubicación. El usuario puede anular la solicitud sin especificar ninguna información. Si se especifica información, primero responderá a la llamada de emergencia el proveedor de servicios de emergencia para verificar la ubicación antes de enrutar la llamada al operador PSAP (Punto de respuesta de seguridad pública), o lo que es lo mismo, al operador del 911.
        
          - **No requerido**	No se solicitará al usuario que especifique una ubicación. Al realizar una llamada sin información de ubicación, el proveedor de servicios de emergencia responderá a la llamada y solicitará que se especifique una ubicación.
        
          - **Declinación de responsabilidades**   Esta opción es la misma que **Required,** excepto que el usuario no puede descartar el mensaje sin especificar la información de ubicación. El usuario podrá completar una llamada de emergencia, pero no podrá completarse ninguna otra llamada sin especificar la información. Además, puede mostrarse al usuario un texto de declinación de responsabilidades para alertarle sobre las consecuencias de negarse a especificar información de contacto. Para establecer el texto de declinación de responsabilidades, debe usar el Shell de administración de Skype Empresarial Server para ejecutar el cmdlet **Set-CsLocationPolicy** o el cmdlet **New-CsLocationPolicy** con el parámetro EnhancedEmergencyServiceDisclaimer. Para obtener más información, [vea Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Use la ubicación para los** servicios de emergencia Skype Empresarial puede usar la información de ubicación por diversos motivos (por ejemplo, para notificar a los compañeros de equipo de su ubicación actual). Seleccione esta casilla para garantizar que la información de ubicación solo está disponible para su uso en una llamada de emergencia.
    
      - **Uso de RTC**	Uso que se hará de la red telefónica conmutada (RTC) para averiguar qué ruta de voz se usa para enrutar llamadas de emergencia realizadas desde clientes que usen este perfil. La ruta asociada con este uso debe hacer referencia a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que desvíe las llamadas de emergencia al PSAP (Punto de respuesta de seguridad pública) más cercano.
    
      - **Número de teléfono de emergencia**   El número que se marca para tener acceso a los servicios de emergencia. En los EE. UU. el número es 911. La cadena debe estar formada por dígitos del 0 al 9 y puede contener de uno a diez dígitos.
    
      - **Máscara de marcado de emergencia**   Un número que al marcarlo se convertirá en el valor del número de teléfono de emergencia. Por ejemplo, si especifica el valor "212" en este campo y el número de teléfono de emergencia tiene el valor "911", cuando un usuario marca 212, la llamada se realizará al 911. Esto permite marcar números de emergencia alternativos y seguir teniendo acceso a los servicios de emergencia (por ejemplo, si una persona de un país o una región con otro número de emergencia intenta marcar el número de su país o región, en lugar del número del país o la región donde se encuentra.) Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. La longitud máxima de la cadena es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
      

        > [!IMPORTANT]  
        > Compruebe que el valor de la máscara de marcado no coincide con ningún número del intervalo de la órbita de estacionamiento de llamadas. El enrutamiento del estacionamiento de llamadas tiene prioridad sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos existentes en la órbita de estacionamiento de llamadas, haga clic en  **Características de voz** en la barra de navegación izquierda y seleccione **Estacionamiento de llamadas**. 

    
      - **URI de notificación**	Uno o más identificadores uniformes de recursos (URI) del SIP que se notificarán al realizar una llamada de emergencia. Por ejemplo, el departamento de seguridad de la empresa puede recibir una notificación por mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, se incluirá dicha ubicación en la notificación. Se pueden incluir varios URI del SIP, separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". No se admiten listas de distribución. La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo "sip:". Antes de que haga clic en el campo URI de notificación aparecerá un ejemplo.
    
      - **URI de conferencia**   El URI del SIP, en este caso el número de teléfono, de un tercero que entrará en conferencia en cualquier llamada de emergencia realizada. Por ejemplo, el departamento de seguridad de la empresa puede recibir una llamada cuando se realiza una llamada de emergencia y escuchar o participar en la conversación (según el valor proporcionado en el campo **Modo de conferencia**). La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo sip:. Aparece un ejemplo hasta que se hace clic dentro del campo.
    
      - **Modo de conferencia**   Si especifica un valor en el campo  **URI de conferencia**, el  **Modo de conferencia** determina si puede participar un tercero en la llamada o si solo puede escucharla. Especifique una de las opciones siguientes:
        
          - **Unidireccional**   El tercero solo puede escuchar la conversación entre el autor de la llamada y el operador del servicio de emergencia.
        
          - **Bidireccional**   El tercero puede escuchar y participar en la conversación entre el autor de la llamada y el operador del servicio de emergencia.

6.  Haga clic en **Confirmar**.


    > [!IMPORTANT]  
    > Cuando crea una directiva de usuario, no se aplica inicialmente a ningún usuario o sitio de red. Para aplicar la directiva a un usuario, haga clic en **Usuarios** en la barra de navegación izquierda. Busque al usuario al que desea aplicarle la directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En la **página Editar usuario del** servidor,  seleccione la nueva directiva de ubicación en la lista desplegable Directiva de ubicación y, a continuación, haga clic en **Confirmar**.<BR>Para aplicar la directiva a un sitio de red, haga clic en **Configuración de red** en la barra de navegación izquierda y seleccione **Sitio**. Busque el sitio de red al que desea aplicarle la directiva. En el menú **Editar**, haga clic en **Mostrar detalles**. En la página **Editar sitio**, seleccione una nueva directiva de ubicación de la lista desplegable **Directiva de ubicación** y, a continuación, haga clic en **Confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar una directiva de ubicación en el Panel Skype Empresarial Server control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva **de ubicación.**

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página  **Editar directiva de ubicación**, modifique los campos según sea necesario (para obtener más información, consulte el paso 5 de los procedimientos "Para crear una nueva directiva de ubicación" expuestos anteriormente en este tema).

7.  Haga clic en **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Eliminar una directiva de ubicación


1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva **de ubicación.**

4.  En la página  **Directiva de ubicación**, seleccione la directiva de ubicación que desea eliminar.
   
    > [!NOTE]  
    > Puede eliminar más de una ubicación en la misma operación. Para hacerlo, pulse CTRL y seleccione varias directivas manteniendo pulsada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en **Seleccionar todo** en el menú **Editar**.


5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

    > [!IMPORTANT]  
    > No puede eliminar la directiva de ubicación Global. Si trata de eliminar la directiva Global recibirá un mensaje de advertencia y las propiedades de dicha directiva se restablecerán a sus valores predeterminados.


## <a name="see-also"></a>Consulte también

[Crear o modificar sitios de red](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)