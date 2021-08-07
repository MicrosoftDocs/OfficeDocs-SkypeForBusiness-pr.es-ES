---
title: Directiva de ubicación Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Puede configurar directivas de ubicación para determinar si enhanced 9-1-1 (E9-1-1) está habilitado y cómo se usa, así como cómo se usa la información de ubicación para los usuarios y los contactos.
ms.openlocfilehash: 1102aeccb6b9e91e29526b6512c7742b766514a15a5d6e13e0e1c00698d866a1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305762"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Directiva de ubicación: Crear nuevos o editar los existentes

Puede configurar directivas de ubicación para determinar si enhanced 9-1-1 (E9-1-1) está habilitado y cómo se usa, así como cómo se usa la información de ubicación para los usuarios y los contactos.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la directiva de ubicación que está creando o modificando: global, de sitio o de usuario.

- **Nombre** Cada directiva de ubicación requiere un nombre. Las directivas de ubicación global y de sitio tienen un nombre predeterminado que no puede cambiarse. Para las directivas de ubicación de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.

    > [!NOTE]
    > Una vez guardada la directiva de ubicación, el nombre no se puede cambiar.

- **Habilitar 9-1-1 mejorado (E9-1-1)** Active esta casilla para habilitar E9-1-1 para los usuarios que tienen asignada esta directiva de ubicación.

- **Ubicación** Especifique si se solicita a los usuarios información de ubicación:

  - **Obligatorio** Seleccione esta opción si se va a solicitar a los usuarios información de ubicación cuando su cliente se registre en una nueva ubicación. Los usuarios pueden rechazar la solicitud sin especificar información de ubicación.

  - **No necesario** Seleccione esta opción si no se va a solicitar información de ubicación a los usuarios.

  - **Declinación de responsabilidades** Seleccione esta opción si se va a solicitar información de ubicación a los usuarios, pero verá un mensaje de declinación de responsabilidades si rechazan el mensaje sin especificar la información. Los usuarios pueden realizar una llamada de emergencia, pero ninguna otra llamada hasta que especifiquen la información de ubicación.

- **Usar la ubicación solo para E9-1-1** Active esta casilla si la información de ubicación se usará solo para llamadas de emergencia.

- **Uso de RTC** Seleccione el uso de la red telefónica conmutada (RTC) que se usará para determinar qué ruta de voz se usará para enrutar llamadas de emergencia de clientes que usan este perfil. La ruta asociada a este uso debe apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al Punto de respuesta de seguridad pública (PSAP) más cercano. Las opciones son **Interno**, **Local** o **Larga distancia**.

- **Número de marcado E9-1-1** Especifique el número que se marca para llegar a los servicios de emergencia.

- **Máscara de marcado E9-1-1** Especifique un número que marca un usuario, que luego se convierte en el número de marcado de emergencia. Por ejemplo, especifique un valor de 212 en este campo para que un usuario pueda marcar 212 para tener acceso a servicios de emergencia. Esto permite que se marquen números de emergencia alternativos y que la llamada llegue a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número del país o región en el que se encuentra actualmente). Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. La longitud máxima de la cadena es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.

    > [!IMPORTANT]
    > Asegúrese de que la máscara de marcado no es la misma que el número del intervalo numérico de estacionamiento de llamadas, ya que el enrutamiento de estacionamiento de llamadas prevalece sobre la conversión de cadenas de marcado de emergencia. Para ver los intervalos de números de estacionamiento de llamadas, haga clic en **Características** de voz en la barra de navegación izquierda y, a continuación, haga clic en **Estacionamiento de llamadas.**

- **URI de notificación** Especifique uno o varios URI de SIP que se notificarán cuando se realiza una llamada de emergencia. Por ejemplo, escriba el URI del SIP del departamento de seguridad de la empresa para notificar al personal de seguridad mediante mensajería instantánea si se realiza una llamada de emergencia. Si la ubicación del autor de la llamada está disponible, la ubicación se incluye en la notificación. Se pueden incluir varios URI del SIP, separados por comas, en una lista. Por ejemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo "sip:". También puede especificar listas de distribución.

- **URI de conferencia** Especifique el URI de SIP (número de teléfono, en este caso) para que un tercero pueda ser conferenciado en llamadas de emergencia. Por ejemplo, escriba el número de teléfono del departamento de seguridad de la empresa para que reciba una llamada cuando se realice una llamada de emergencia. La configuración del **modo de conferencia** determina si el tercero puede participar o solo escuchar en la llamada. La cadena debe tener entre 1 y 256 caracteres de longitud y debe comenzar con el prefijo sip:.

- **Modo de conferencia** Si especificó un valor para **el URI de** conferencia, establezca este campo en uno de los siguientes valores:

  - **Un solo sentido** Especifica que el tercero solo puede escuchar la llamada entre el autor de la llamada y el operador PSAP.

  - **Dos vías** Especifica que el tercero puede participar en la llamada entre el autor de la llamada y el operador PSAP.

Para obtener más información Telefonía IP empresarial características y funcionalidades del servicio de emergencia, vea [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con directivas de ubicación, vea [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) en la documentación de operaciones.