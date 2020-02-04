---
title: Directiva de ubicación crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: 2623e5f3a723dc0ce061109e047961d68bd7badd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686393"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Directiva de ubicación: Crear nueva o editar existente

Puede configurar directivas de ubicación para determinar si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la Directiva de ubicación que está creando o modificando: global, sitio o usuario.

- **Nombre** Cada política de ubicación requiere un nombre. Las directivas de ubicación global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de ubicación de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.

    > [!NOTE]
    > Una vez guardada la directiva de ubicación, el nombre no se puede cambiar.

- **Habilitar enhanced 9-1-1 (E9-1-1)** Seleccione esta casilla para habilitar E9-1-1 para los usuarios que tienen asignada esta directiva de ubicación.

- **Ubicación** Especificar si se pide a los usuarios información de Ubicación:

  - **Necesario** Seleccione esta opción si se le solicitará a los usuarios información de la ubicación cuando su cliente se registre en una nueva ubicación. Los usuarios pueden rechazar la solicitud sin especificar información de ubicación.

  - **No es necesario** Seleccione esta opción si no se le solicitará la información de la ubicación a los usuarios.

  - **Renuncia** Seleccione esta opción si se le solicitará la información de la ubicación a los usuarios, pero verá un mensaje de renuncia si rechaza el aviso sin especificar la información. Los usuarios pueden realizar una llamada de emergencia, pero ninguna otra llamada, hasta que especifiquen la información de ubicación.

- **Usar la ubicación solo para E9-1-1** Seleccione esta casilla si la información de ubicación solo se va a usar para llamadas de emergencia.

- **Uso de RTC** Seleccione el uso de la red de telefonía pública conmutada (RTC) que se usará para determinar qué ruta de voz se usará para el enrutamiento de llamadas de emergencia de clientes que usan este perfil. La ruta asociada a este uso necesita apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano. Las opciones son **Interno**, **Local** o **Larga distancia**.

- **Número de marcado E9-1-1** Especifique el número que se marca para alcanzar los servicios de emergencia.

- **Máscara de marcado E9-1-1** Especifique el número que un usuario marca, que se traducirá al número de emergencia. Por ejemplo, escriba un valor de 212 en este campo para que el usuario pueda marcar 212 para comunicarse con servicios de emergencia. Esto permite que se marquen números de emergencia alternativos y siga haciendo que las llamadas lleguen a servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número de la país o región en el que se encuentran actualmente). Puede definir varias máscaras de marcado de emergencia si separa los valores con signos de punto y coma. Por ejemplo, 212; 414. La longitud máxima de la cadena es de 100 caracteres. Cada carácter debe ser un dígito del 0 al 9.

    > [!IMPORTANT]
    > Procure que la máscara de marcado no sea la misma que el número del intervalo de números de estacionamiento de llamadas, ya que el enrutamiento de estacionamiento de llamadas prevalece sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos de números de estacionamiento de llamadas, haga clic en **características de voz** en la barra de navegación izquierda y luego haga clic en **llamar a estacionamiento**.

- **URI de notificación** Especifique uno o más URI SIP a los que se va a notificar cuando se realice una llamada de emergencia. Por ejemplo, escriba el URI del SIP del departamento de seguridad de la empresa para notificar al personal de seguridad a través de mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación de la persona que llama está disponible, la ubicación se incluye en la notificación. Se pueden incluir varios URI del SIP separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo "sip:". También puede especificar listas de distribución.

- **URI de conferencia** Especifique el URI del SIP (en este caso, el número de teléfono) para que un tercero se Conferencia en las llamadas de emergencia. Por ejemplo, escriba el número de teléfono del departamento de seguridad de la empresa para que reciba una llamada cuando se realice una llamada de emergencia. La configuración del **modo de conferencia** determina si el tercero puede participar o solo escuchar en la llamada. La cadena necesita tener entre 1 y 256 caracteres de longitud y necesita comenzar por el prefijo sip:.

- **Modo de conferencia** Si especificó un valor para el URI de la **Conferencia**, establezca este campo en uno de los valores siguientes:

  - **Unidireccional** Especifica que el tercero solo puede escuchar la llamada entre el operador de llamadas y el operador PSAP.

  - **Bidireccional** Especifica que el tercero puede participar en la llamada entre la persona que llama y el operador PSAP.

Para obtener más información sobre las características y capacidades del servicio de emergencia de Enterprise Voice, consulte [información general sobre E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planificación. For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.


