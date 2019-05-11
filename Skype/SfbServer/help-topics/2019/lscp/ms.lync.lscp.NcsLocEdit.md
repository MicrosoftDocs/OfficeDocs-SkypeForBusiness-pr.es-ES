---
title: Directiva de ubicación crear nuevos o editar los existentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: 836435704ddd27356be2d39fdd278891b2bbfcd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891148"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Directiva de ubicación: Crear nueva o editar existente

Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la directiva de ubicación que está creando o modificando: global, sitio o usuario.

- **Nombre** Cada directiva de ubicación requiere un nombre. Las directivas de ubicación global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de ubicación de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.

    > [!NOTE]
    > Una vez guardada la directiva de ubicación, el nombre no se puede cambiar.

- **Habilitar 9-1-1 mejorado (E9-1-1)** Active esta casilla de verificación para habilitar E9-1-1 para los usuarios que están asignados a esta directiva de ubicación.

- **Ubicación** Especifique si los usuarios se solicita información de la ubicación:

  - **Obligatorio** Seleccione esta opción si los usuarios que se le solicite información de ubicación cuando su cliente se registra en una nueva ubicación. Los usuarios pueden rechazar la solicitud sin especificar información de ubicación.

  - **No se requiere** Seleccione esta opción si los usuarios no tienen se le pida información de ubicación.

  - **Declinación de responsabilidades** Seleccione esta opción si los usuarios son que se le solicite información de ubicación, pero aparecerá un mensaje de declinación de responsabilidades si la rechaza el símbolo del sistema sin tener que especificar la información. Los usuarios pueden realizar una llamada de emergencia, pero ninguna otra llamada, hasta que especifiquen la información de ubicación.

- **Usar ubicación para E9-1-1 solo** Seleccione esta casilla de verificación si es información de ubicación que se usará únicamente para las llamadas de emergencia.

- **Uso de RTC** Seleccione el uso de telefónica conmutada (RTC) de red que se usará para determinar qué ruta de voz se usará para enrutar las llamadas de emergencias desde los clientes que usan este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano. Las opciones son **Interno**, **Local** o **Larga distancia**.

- **Número de marcado de E9-1-1** Especifique el número que se marca para llegar a los servicios de emergencia.

- **Máscara de marcado de E9-1-1** Especifique un número que un usuario marca, que se traduce, a continuación, en número de emergencia. Por ejemplo, escriba un valor de 212 en este campo para que un usuario puede marcar 212 para llegar a los servicios de emergencia. Esto permite que los números de emergencias alternativos se debe marcar y seguir teniendo la llamada llegar a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número diferente de emergencia intenta marcar que país o región del número en vez del número de la país o región que se encuentran actualmente en). Puede definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212; 414. La longitud máxima de la cadena es de 100 caracteres. Cada carácter debe ser un dígito de 0 a 9.

    > [!IMPORTANT]
    > Procure que la máscara de marcado no sea la misma que el número del intervalo de números de estacionamiento de llamadas, ya que el enrutamiento de estacionamiento de llamadas prevalece sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos de números de estacionamiento de llamadas, haga clic en **Características de voz** en la barra de navegación izquierdo y, a continuación, haga clic en **Estacionamiento de llamadas**.

- **URI de notificación** Especifique uno o más los URI de SIP para recibir una notificación cuando se realiza una llamada de emergencia. Por ejemplo, escriba el URI del SIP del departamento de seguridad de la empresa para notificar al personal de seguridad a través de mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, la ubicación se incluye en la notificación. Se pueden incluir varios URI del SIP separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". También puede especificar listas de distribución.

- **URI de conferencia** Especifique el URI de SIP (número de teléfono, en este caso) para que un tercero ser incluirse en la conferencia a las llamadas de emergencia. Por ejemplo, escriba el número de teléfono del departamento de seguridad de la empresa para que reciba una llamada cuando se realice una llamada de emergencia. La configuración del **modo de conferencia** determina si el tercero puede participar o solo escuchar en la llamada. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:.

- **Modo de conferencia** Si ha especificado un valor para el **URI de conferencia**, establezca este campo en uno de los siguientes valores:

  - **Unidireccional** Especifica que el tercero solo puede escuchar a la llamada entre el autor de la llamada y el operador del servicio de emergencia.

  - **Bidireccional** Especifica que el tercero puede participar en la llamada entre el autor de la llamada y el operador del servicio de emergencia.

Para obtener información detallada sobre las características de servicios de emergencia de Enterprise Voice y funciones, vea [información general de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planeación. For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.


