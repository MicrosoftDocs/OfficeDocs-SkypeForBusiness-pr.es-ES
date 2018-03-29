---
title: Política de ubicación crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: cc2d5119e4bb21badf96dcf24099844ffffd0639
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy-create-new-or-edit-existing"></a>Directiva de ubicación: Crear nueva o editar existente
 
Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Ámbito de aplicación** Identifica el ámbito de la política de ubicación que está creando o modificando: global, sitio o usuario.
    
- **Nombre** Cada directiva de ubicación requiere un nombre. Las directivas de ubicación global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de ubicación de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.
    
    > [!NOTE]
    > Una vez guardada la directiva de ubicación, el nombre no se puede cambiar. 
  
- **Habilitar mejorada 9-1-1 (E9-1-1)** Active esta casilla de verificación Habilitar E9-1-1 para los usuarios que están asignados a esta directiva de ubicación.
    
- **Ubicación** Especifica si se pide a los usuarios información de la ubicación:
    
  - **Requerido** Seleccione esta opción si los usuarios que se le pida la información de la ubicación cuando el cliente se registra en una nueva ubicación. Los usuarios pueden rechazar la solicitud sin especificar información de ubicación.
    
  - **No se requiere** Seleccione esta opción si los usuarios no se le pida información de ubicación.
    
  - **Descargo de responsabilidad** Seleccione esta opción si los usuarios son que se le pida la información de ubicación, pero aparecerá un mensaje de renuncia si rechaza el símbolo del sistema sin especificar la información. Los usuarios pueden realizar una llamada de emergencia, pero ninguna otra llamada, hasta que especifiquen la información de ubicación.
    
- **Ubicación de uso para E9-1-1 sólo** Seleccione esta casilla de verificación si es información de ubicación que se utilizará sólo para llamadas de emergencia.
    
- **Uso PSTN** Seleccione el uso de telefónica pública conmutada (RTC) de la red que se utilizará para determinar qué ruta de voz se utilizará para llamadas de emergencia enrutamiento de clientes que usan este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano. Las opciones son **Interno**, **Local** o **Larga distancia**.
    
- **Número de marcado E9-1-1** Especifique el número que se marca para llegar a los servicios de emergencia.
    
- **Máscara de marcado E9-1-1** Especifique un número que llama a un usuario, que luego se convierte en el número de acceso telefónico de emergencia. Por ejemplo, escriba un valor de 212 en este campo para que un usuario puede marcar 212 para llegar a los servicios de emergencia. Esto permite que los números de emergencia alternativos marcar y seguir teniendo la llamada llegue a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número diferente de emergencia intenta marcar que país o región del número en vez del número de la país o región que están actualmente en). Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. La longitud máxima de la cadena es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
    
    > [!IMPORTANT]
    > Procure que la máscara de marcado no sea la misma que el número del intervalo de números de estacionamiento de llamadas, ya que el enrutamiento de estacionamiento de llamadas prevalece sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos numéricos parque de llamada, haga clic en **Características de voz** en la barra de navegación de la izquierda y, a continuación, haga clic en **Llamada Park**. 
  
- **URI de notificación** Especifique uno o varios URI del SIP que se le notifique cuando se realiza una llamada de emergencia. Por ejemplo, escriba el URI del SIP del departamento de seguridad de la empresa para notificar al personal de seguridad a través de mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del llamador está disponible, la ubicación se incluye en la notificación. Se pueden incluir varios URI del SIP separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". También puede especificar listas de distribución.
    
- **Conferencia de URI** Especifique el URI de SIP (en este caso, número de teléfono) de un tercero se conferenced en para llamadas de emergencia. Por ejemplo, escriba el número de teléfono del departamento de seguridad de la empresa para que reciba una llamada cuando se realice una llamada de emergencia. La configuración del **modo de conferencia** determina si el tercero puede participar o solo escuchar en la llamada. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:.
    
- **Modo conferencia** Si especifica un valor para el **URI de la conferencia**, establezca este campo en uno de los siguientes valores:
    
  - **Unidireccional** Especifica que el tercero sólo puede escuchar a la llamada entre el llamador y el operador PSAP.
    
  - **Ambos sentidos** Especifica que el tercero puede participar en la llamada entre el llamador y el operador PSAP.
    
Para obtener más información acerca de capacidades y características de Telefonía IP empresarial servicio de emergencia, vea [Resumen de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planeamiento. Para obtener más información acerca de cómo trabajar con las políticas de ubicación, vea [Configurar la directiva de ubicación](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) en la documentación de las operaciones.
  

