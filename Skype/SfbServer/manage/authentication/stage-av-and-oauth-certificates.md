---
title: Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
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
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumen: stage AV and OAuth certificates for Skype for Business Server.'
ms.openlocfilehash: a2586e9ebda1bae1605fd6033681b469e6731b8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806560"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
 
**Resumen:** Stage AV and OAuth certificates for Skype for Business Server.
  
Las comunicaciones de audio y vídeo (A/V) son un componente clave de Skype Empresarial Server. Las características como el uso compartido de aplicaciones y las conferencias de audio y vídeo dependen de los certificados asignados al servicio perimetral A/V, específicamente el servicio de autenticación A/V.
  
> [!IMPORTANT]
> Esta nueva característica está diseñada para funcionar con el servicio perimetral A/V y el certificado OAuthTokenIssuer. Otros tipos de certificado se pueden aprovisionar junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiarán del comportamiento de coexistencia que tendrá el certificado de servicio perimetral A/V.
  
Los cmdlets de PowerShell del Shell de administración de Skype Empresarial Server que se usan para administrar certificados de Skype Empresarial Server se refieren al certificado de servicio perimetral A/V como el tipo de certificado AudioVideoAuthentication y el certificado OAuthServer como typeOAuthTokenIssuer. Para el resto de este tema y para identificar de forma exclusiva los certificados, se hará referencia a ellos mediante el mismo tipo de identificador, AudioVideoAuthentication yOAuthTokenIssuer.
  
El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan desde atributos del certificado, y cuando el certificado expira, se producirá la pérdida de conexión y el requisito de volverse a unir con un nuevo token generado por el nuevo certificado. Una nueva característica de Skype Empresarial Server solucionará este problema: la capacidad de realizar una fase de un nuevo certificado antes de que expire el antiguo y permitir que ambos certificados sigan funcionando durante un período de tiempo. Esta característica usa la funcionalidad actualizada en el cmdlet Set-CsCertificate Shell de administración de Skype Empresarial Server. El nuevo parámetro -Roll, con el parámetro existente -EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. Comenzando por la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:
  
> [!TIP]
> Con los cmdlets del Shell de administración de Skype Empresarial Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. El uso del Asistente para certificados en el Asistente para la implementación de  Skype Empresarial Server le ayuda a crear certificados, pero suele ser del tipo predeterminado que une todos los certificados que usa el servidor perimetral en un solo certificado. La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado. Puede aprovisionar y organizar un certificado del tipo predeterminado pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará del ensayo. Un usuario que participe en (por ejemplo) una conversación de mensajería instantánea cuando expire el certificado tendrá que cerrar sesión y volver a iniciarla para usar el nuevo certificado asociado con el servicio perimetral de acceso. Se producirá un comportamiento similar para un usuario que participa en una conferencia web mediante el servicio perimetral de conferencia web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. El certificado se crea y administra en un solo lugar y el certificado se almacena en el almacén de administración central para todos los demás servidores.
  
Se necesitan detalles adicionales para comprender por completo sus opciones y requisitos al usar el cmdlet Set-CsCertificate y al usarlo para organizar certificados anteriores al certificado actual que expira. El parámetro -Roll es importante, pero esencialmente un único propósito. Si lo define como un parámetro, le está diciendo a Set-CsCertificate que va a proporcionar información sobre el certificado que se verá afectado definido por -Type (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado será efectivo definido por -EffectiveDate.
  
 **-Roll:** el parámetro -Roll es obligatorio y tiene dependencias que se deben proporcionar junto con él. Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:
  
 **-EffectiveDate:** el parámetro -EffectiveDate define cuándo el nuevo certificado se volverá co-activo con el certificado actual. -EffectiveDate puede estar cerca de la fecha de expiración del certificado actual o puede ser un período de tiempo más largo. Un mínimo recomendado -EffectiveDate para el certificado AudioVideoAuthentication sería de 8 horas, que es la duración de token predeterminada para los tokens de servicio perimetral av emitidos con el certificado AudioVideoAuthentication.
  
Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.
  
 **-Thumbprint**: la huella digital es un atributo del certificado que es único para dicho certificado. El parámetro -Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.
  
 **-Type:** el parámetro -Type puede aceptar un único tipo de uso de certificado o una lista separada por comas de tipos de uso de certificados. Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, el servicio perimetral A/V y el servicio de autenticación AV usan AudioVideoAuthentication. Si decide realizar fases y aprovisionar certificados de otro tipo al mismo tiempo, debe tener en cuenta el plazo mínimo efectivo más largo necesario para los certificados. Por ejemplo, debe realizar una fase de certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. Su mínimo -EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no quieres realizar una fase del certificado AudioVideoAuthentication con un tiempo de ejecución de 24 horas, escándalo por separado con un EffectiveDate que sea más según tus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de servicio perimetral A/V con parámetros -Roll y -EffectiveDate

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicita una renovación o un nuevo certificado AudioVideoAuthentication con clave privada exportable para el certificado existente en el servicio perimetral A/V.
    
3. Importe el nuevo certificado AudioVideoAuthentication al servidor perimetral y al resto del servidor perimetral del grupo de servidores (si tiene implementado un grupo de servidores).
    
4. Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro -Roll con el parámetro -EffectiveDate. La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas). Esto nos da una hora en la que el certificado debe establecerse en activo y es -EffectiveDate \<string\> : "22/7/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para un grupo de servidores perimetrales, debe tener todos los certificados AudioVideoAuthentication implementados y aprovisionados por la fecha y hora definidas por el parámetro -EffectiveDate del primer certificado implementado para evitar posibles interrupciones en las comunicaciones A/V debido a que el certificado anterior expira antes de que todos los tokens de cliente y consumidor se hayan renovado con el nuevo certificado. 
  
    El Set-CsCertificate comando con los parámetros -Roll y -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Un comando Set-CsCertificate de ejemplo:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate debe tener formato para que coincida con la configuración de región e idioma del servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.) 
  
Para comprender mejor el proceso que Set-CsCertificate, -Roll y -EffectiveDate usan para crear un nuevo certificado para emitir nuevos tokens AudioVideoAuthentication mientras se sigue usando un certificado existente para validar AudioVideoAuthentication que usan los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso. En el siguiente ejemplo, el administrador determina que el certificado de servicio perimetral A/V debe expirar a las 14:00:00 del 22/07/2015. Solicita y recibe un nuevo certificado e lo importa a cada servidor perimetral de su grupo de servidores. A las 2 a.m. del 22/07/2015, comienza a ejecutar Get-CsCertificate con -Roll, -Thumbprint igual a la cadena de huella digital del nuevo certificado y -EffectiveTime establecido en 07/22/2015 6:00:00 AM. Ejecuta este comando en cada servidor perimetral.
  
![Uso de los parámetros Roll y EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Fase**|
|:-----|:-----|
|1   <br/> |Inicio: 22/7/2015 12:00:00 AM  <br/> The current AudioVideoAuthentication certificate is due to expire at 2:00:00 PM on 7/22/2015. Esto se determina mediante la marca de tiempo de expiración en el certificado. Planee el reemplazo y la sustitución del certificado para que se contempló una superposición de 8 horas (duración de token predeterminada) antes de que el certificado existente alcance el tiempo de expiración. El plazo de las 2:00:00 a.m. se usa en este ejemplo para permitir al administrador el tiempo adecuado para colocar y aprovisionar los nuevos certificados antes del tiempo efectivo de las 6:00:00 a.m.  <br/> |
|2   <br/> |22/7/2015 2:00:00 AM - 22/7/2015 5:59:59 AM  <br/> Establecer certificados en servidores perimetrales con un tiempo efectivo de 6:00:00 AM (el plazo de 4 horas es para este ejemplo, pero puede ser más largo) con Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |22/7/2015 6:00 AM - 22/7/2015 14:00  <br/> Para validar tokens, el nuevo certificado se intenta primero y, si el nuevo certificado no puede validar el token, se intenta el certificado antiguo. Este proceso se usa para todos los tokens durante el período de superposición de 8 horas (duración predeterminada del token).  <br/> |
|4   <br/> |Final: 22/7/2015 2:00:01 PM  <br/> El certificado antiguo ha expirado y el nuevo certificado ha tomado el control. El certificado antiguo se puede quitar de forma segura Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Cuando se alcanza el tiempo efectivo (22/7/2015 6:00:00 AM), el nuevo certificado emite todos los tokens nuevos. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el certificado antiguo ha expirado (22/7/2015 2:00:00 PM), los tokens solo serán validados por el nuevo certificado. El certificado antiguo se puede quitar de forma segura mediante el cmdlet Remove-CsCertificate con el parámetro -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado OAuthTokenIssuer con parámetros -Roll y -EffectiveDate

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicite una renovación o un nuevo certificado OAuthTokenIssuer con clave privada exportable para el certificado existente en el servidor front-end.
    
3. Importe el nuevo certificado OAuthTokenIssuer a un servidor front-end del grupo de servidores (si tiene implementado un grupo de servidores). El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que replicar y renovar en cualquier servidor de su implementación. El servidor front-end se usa como ejemplo.
    
4. Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro -Roll con el parámetro -EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas. 
    
    El Set-CsCertificate comando con los parámetros -Roll y -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Un comando Set-CsCertificate de ejemplo:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate debe tener formato para que coincida con la configuración de región e idioma del servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.) 
  
Cuando se alcanza el tiempo efectivo (21/7/2015 1:00:00 a.m.), el nuevo certificado emite todos los tokens nuevos. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el certificado antiguo ha expirado (22/7/2015 2:00:00 PM), los tokens solo serán validados por el nuevo certificado. El certificado antiguo se puede quitar de forma segura mediante el cmdlet Remove-CsCertificate con el parámetro -Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vea también

[Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Skype Empresarial Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
