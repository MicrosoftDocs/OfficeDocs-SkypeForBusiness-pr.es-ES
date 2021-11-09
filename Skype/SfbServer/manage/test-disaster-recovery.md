---
title: Pruebas de recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Realizar una recuperación del sistema para un servidor Skype Empresarial Server grupo de servidores para probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: 2d6fa097061b470814887f1e13eaf4748de6e4f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863507"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Pruebas de recuperación ante desastres en Skype Empresarial Server

Realice una recuperación del sistema para un servidor Skype Empresarial Server grupo de servidores para probar el proceso de recuperación ante desastres documentado. Esta prueba simulará un error de hardware completo para un servidor y ayudará a garantizar que los recursos, planes y datos están disponibles para la recuperación. Intente girar el foco de la prueba cada mes para que su organización pruebe el error de un servidor diferente u otro equipo cada vez. 

Tenga en cuenta que la programación por la que las organizaciones realizan pruebas de recuperación ante desastres variará. Es muy importante que las pruebas de recuperación ante desastres no se ignoren ni se ignoren. 

Exporte Skype Empresarial Server topología, directivas y opciones de configuración a un archivo. Entre otras cosas, este archivo puede usarse para restaurar esta información en el almacén de administración central después de que una actualización, un error de hardware o algún otro problema haya provocado la pérdida de datos.

Importe su Skype Empresarial Server, directivas y opciones de configuración al almacén de administración central o al equipo local, como se muestra en los siguientes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para hacer una copia de seguridad de los datos de producción:

- Realice una copia de seguridad de las bases de datos RTC y LCSLog mediante el proceso SQL Server de copia de seguridad estándar para volcar la base de datos en un dispositivo de volcado de cinta o archivo.
- Use una aplicación de copia de seguridad de terceros para realizar una copia de seguridad de los datos en el archivo o en cinta.
- Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.
- Use la copia de seguridad del sistema de archivos o la copia de seguridad de terceros para hacer una copia de seguridad del contenido de la reunión y los registros de cumplimiento.
- Use la Export-CsConfiguration de línea de comandos para hacer una copia de seguridad Skype Empresarial Server configuración.

El primer paso del procedimiento de conmutación por error incluye un movimiento forzado de usuarios del grupo de producción al grupo de recuperación ante desastres. Se trata de un movimiento forzado porque el grupo de producción no estará disponible para aceptar la reubicación del usuario.

El Skype Empresarial Server de usuario de movimiento es efectivamente un cambio a un atributo en el objeto de cuenta de usuario, además de una actualización de registros en la base de datos rtc SQL usuario. Estos datos se pueden restaurar desde el dispositivo de volcado de copia de seguridad original desde el SQL Server de producción mediante el proceso de restauración SQL Server estándar o mediante una utilidad de copia de seguridad y restauración de terceros.

Después de restaurar estos datos, los usuarios pueden conectarse eficazmente al grupo de recuperación ante desastres y funcionar de la forma habitual. Para permitir que los usuarios se conecten al grupo de recuperación ante desastres, se requiere un cambio de registro DNS.

Los clientes Skype Empresarial el grupo de servidores de producción a los que se hace referencia mediante la configuración automática y los registros SRV dns de:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para hacer referencia al FQDN de DROCSPool:

- CNAME: SIP.\<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
