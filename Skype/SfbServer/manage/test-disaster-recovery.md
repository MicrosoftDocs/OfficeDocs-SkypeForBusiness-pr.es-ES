---
title: Recuperación ante desastres pruebas en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Realizar una recuperación del sistema para que un Skype para servidor de grupo de servidores de Business Server probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: d401d27c1cc0f5b04c6e256a1e55f6847c9c35ba
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222726"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Recuperación ante desastres pruebas en Skype para Business Server

Realizar una recuperación del sistema para que un Skype para servidor de grupo de servidores de Business Server probar el proceso de recuperación ante desastres documentado. Esta prueba para simular un error de hardware completo para un solo servidor y le ayudará a garantizar que los recursos, los planes y los datos están disponibles para la recuperación. Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos. 

Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas. 

Exportar su Skype para la topología, las directivas y opciones de configuración de Business Server a un archivo. Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.

Importar su Skype para la topología de servidor empresarial, directivas y opciones de configuración en el almacén de Administración Central o en el equipo local, tal como se muestra en los siguientes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para realizar una copia de seguridad de los datos de producción:

- Copia de seguridad de las bases de datos RTC y LCSLog mediante el estándar SQL Server de copia de seguridad proceso a fin de volcado de la base de datos a un dispositivo de volcado de archivo o una cinta.
- Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.
- Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.
- Usar la copia de seguridad de archivos del sistema o una copia de seguridad de terceros para realizar una copia de seguridad de registros de contenido y cumplimiento de normas de la reunión.
- Use la herramienta de línea de comandos de Export-CsConfiguration para hacer una copia de seguridad de Skype para la configuración de Business Server.

El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres. Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.

El Skype para el proceso de usuario de movimiento de Business Server es realmente un cambio en un atributo en el objeto de cuenta de usuario además de una actualización de registro en la base de datos de SQL de RTC. Estos datos pueden restaurarse desde el dispositivo de volcado de copia de seguridad original de la producción SQL Server utilizando el proceso de restauración de SQL Server standard, o un tercero copia de seguridad y restauración utilidad.

Una vez se hayan restaurado los datos, los usuarios eficazmente pueden conectarse al grupo de servidores de recuperación ante desastres y funcionan como de costumbre. Para habilitar a los usuarios conectarse al grupo de servidores de recuperación ante desastres, se necesitarán un cambio de registro de DNS.

La producción Skype para grupo de negocio se indicará por los clientes mediante la configuración automática y los registros DNS SRV:

- SRV: _sip._tls. \<dominio > /CNAME: SIP. \<dominio >
- CNAME: SIP. \<dominio > /cvc-pool-1. \<dominio >

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:

- CNAME: SIP.<domain> / DROCSPool. \<dominio >
- SIP. \<dominio >
- AV.\<dominio >
- webconf. \<dominio >
