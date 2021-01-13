---
title: Pruebas de recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Realizar una recuperación del sistema para un servidor de grupo de Skype Empresarial Server para probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832820"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Pruebas de recuperación ante desastres en Skype Empresarial Server

Realice una recuperación del sistema para un servidor de grupo de Skype Empresarial Server para probar el proceso de recuperación ante desastres documentado. Esta prueba simulará un error de hardware completo para un servidor y le ayudará a garantizar que los recursos, los planes y los datos están disponibles para la recuperación. Intente girar el foco de la prueba cada mes para que su organización pruebe el error de un servidor diferente u otro equipo cada vez. 

Tenga en cuenta que la programación según la cual las organizaciones realizan pruebas de recuperación ante desastres variará. Es muy importante que las pruebas de recuperación ante desastres no se ignoren ni se ignoren. 

Exporte la topología, las directivas y las opciones de configuración de Skype Empresarial Server a un archivo. Entre otras cosas, este archivo puede usarse para restaurar esta información en el almacén de administración central después de una actualización, un error de hardware o algún otro problema que haya provocado la pérdida de datos.

Importe la topología, las directivas y las opciones de configuración de Skype Empresarial Server al almacén de administración central o al equipo local, como se muestra en los comandos siguientes: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para hacer una copia de seguridad de los datos de producción:

- Realice una copia de seguridad de las bases de datos RTC y LCSLog mediante el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un archivo o dispositivo de volcado de cinta.
- Use la aplicación de copia de seguridad de terceros para realizar una copia de seguridad de los datos en un archivo o en cinta.
- Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.
- Use la copia de seguridad del sistema de archivos o la copia de seguridad de terceros para hacer una copia de seguridad del contenido de reuniones y los registros de cumplimiento.
- Use la Export-CsConfiguration de línea de comandos para hacer una copia de seguridad de la configuración de Skype Empresarial Server.

El primer paso del procedimiento de conmutación por error incluye un movimiento forzado de usuarios del grupo de producción al grupo de recuperación ante desastres. Esto será un traslado forzado porque el grupo de producción no estará disponible para aceptar la reubicación del usuario.

El proceso de usuario de movimiento de Skype Empresarial Server es efectivamente un cambio en un atributo en el objeto de cuenta de usuario además de una actualización de registros en la base de datos de SQL RTC. Estos datos se pueden restaurar desde el dispositivo de volcado de copia de seguridad original desde el SQL Server de producción mediante el proceso de restauración estándar de SQL Server o mediante una utilidad de copia de seguridad y restauración de terceros.

Después de restaurar estos datos, los usuarios pueden conectarse de forma eficaz al grupo de recuperación ante desastres y funcionar como de costumbre. Para permitir que los usuarios se conecten al grupo de recuperación ante desastres, se requiere un cambio en el registro DNS.

Los clientes harán referencia al grupo de producción de Skype Empresarial mediante la configuración automática y los registros SRV de DNS de:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para hacer referencia al FQDN de DROCSPool:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- Av.\<domain>
- webconf.\<domain>
