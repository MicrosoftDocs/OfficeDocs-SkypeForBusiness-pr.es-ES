---
title: Ajustar los certificados de AV y OAuth en el servidor de Skype empresarial con el ajuste Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumen: haga una copia de los certificados de AV y OAuth para Skype empresarial Server.'
ms.openlocfilehash: 37edb6843d420ca3387958c54b3db8c72a28be92
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991965"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Ajustar los certificados de AV y OAuth en el servidor de Skype empresarial con el ajuste Set-CsCertificate
 
**Resumen:** Ensayar los certificados de AV y OAuth para Skype empresarial Server.
  
Las comunicaciones de audio/vídeo (A/V) son un componente clave de Skype empresarial Server. Características como el uso compartido de aplicaciones y las conferencias de audio y vídeo dependen de los certificados asignados al servicio perimetral de A/V, específicamente el servicio de autenticación A/V.
  
> [!IMPORTANT]
> Esta nueva característica está diseñada para que funcione con el servicio a/V Edge y el certificado OAuthTokenIssuer. Se pueden aprovisionar otros tipos de certificados junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiará del comportamiento de coexistencia del certificado de servicio perimetral A/V.
  
Los cmdlets de PowerShell de Shell de administración de Skype empresarial Server que se usan para administrar certificados de Skype empresarial Server se refiere al certificado de servicio perimetral a/V como el tipo de certificado AudioVideoAuthentication y el certificado OAuthServer como typeOAuthTokenIssuer. Para el resto de este tema y para identificar los certificados de forma única, se hará referencia a ellos por el mismo tipo de identificador, AudioVideoAuthentication andOAuthTokenIssuer.
  
El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan a partir de atributos del certificado y, cuando el certificado expira, se produce la pérdida de conexión y es necesario volver a unirse con un nuevo token generado por el nuevo certificado. Una nueva característica de Skype empresarial Server mejorará este problema: la capacidad de ensayar un nuevo certificado antes de que venza el antiguo y de permitir que ambos certificados sigan funcionando durante un período de tiempo. Esta característica usa la funcionalidad actualizada en el cmdlet del shell de administración de Skype empresarial Set-CsCertificate. El nuevo parámetro-roll, con el parámetro-EffectiveDate, colocará el nuevo certificado de AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. A partir de la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:
  
> [!TIP]
> Con los cmdlets del shell de administración de Skype empresarial Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. Usar el Asistente para certificados en el Asistente para la implementación de Skype empresarial Server le ayuda a crear certificados, pero suele ser del tipo **predeterminado** que une todos los usos de certificados para el servidor perimetral en un solo certificado. La práctica recomendada si va a usar la característica de certificado rodante es desacoplar el certificado de AudioVideoAuthentication de los otros propósitos del certificado. Puede aprovisionar y ensayar un certificado del tipo predeterminado, pero solo la parte AudioVideoAuthentication del certificado combinado se beneficiará del almacenamiento provisional. Un usuario implicado en una conversación de mensajería instantánea, por ejemplo, en el momento en que expira el certificado, deberá cerrar sesión e iniciarla de nuevo para usar el nuevo certificado asociado con el servicio perimetral de acceso. Se producirá un comportamiento similar para un usuario implicado en una conferencia web con el servicio perimetral de conferencias web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. Cree y administre el certificado en un solo lugar y el certificado se almacena en el almacén de administración central para todos los demás servidores.
  
Es necesario más detalles para comprender completamente sus opciones y requisitos al usar el cmdlet Set-CsCertificate y su uso para organizar certificados antes de que expire el certificado actual. El parámetro-roll es importante, pero esencialmente un único fin. Si lo define como un parámetro, está indicando a set-CsCertificate que le proporcionará información sobre el certificado que se verá afectado según el tipo (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se convierta en efectivo definido por-EffectiveDate.
  
 **-Roll**: el parámetro-roll es obligatorio y tiene dependencias que deben proporcionarse con él. Parámetros obligatorios para definir completamente Qué certificados se verán afectados y cómo se aplicarán:
  
 **-EffectiveDate**: el parámetro-EffectiveDate define cuándo el nuevo certificado volverá a estar activo con el certificado actual. El-EffectiveDate puede estar cerca de la hora de expiración del certificado actual o puede ser un período de tiempo más largo. Un EffectiveDate mínimo recomendado para el certificado de AudioVideoAuthentication sería de 8 horas, que es el token de vigencia predeterminado para los tokens del servicio de borde AV emitido con el certificado de AudioVideoAuthentication.
  
Al ensayar certificados de OAuthTokenIssuer, existen diferentes requisitos para el tiempo de adelanto antes de que el certificado pueda ser efectivo. El tiempo mínimo que el certificado de OAuthTokenIssuer debería tener por su tiempo de adelanto es de 24 horas antes de la fecha de expiración del certificado actual. El tiempo de adelanto ampliado de la coexistencia se debe a que existen otros roles de servidor que dependen del certificado OAuthTokenIssuer (Exchange Server, por ejemplo), lo que tiene un mayor tiempo de retención para la autenticación y la clave de cifrado del certificado cosecha.
  
 **-Huella digital**: la huella digital es un atributo en el certificado que es único para ese certificado. El parámetro-Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.
  
 **-Type**: el parámetro-type puede aceptar un único tipo de uso de certificado o una lista separada por comas de tipos de uso de certificados. Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, escriba AudioVideoAuthentication es para que lo use el servicio A/V Edge y el servicio de autenticación de AV. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el tiempo de adelanto mínimo mínimo requerido para los certificados. Por ejemplo, necesita organizar los certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. El mínimo-EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea ensayar el certificado de AudioVideoAuthentication con un tiempo de adelanto de 24 horas, hágalo por separado con un EffectiveDate que sea más conveniente para sus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de servicio perimetral de A/V con parámetros a-roll y-EffectiveDate

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicite una renovación o un certificado de AudioVideoAuthentication nuevo con una clave privada exportable para el certificado existente en el servicio perimetral A/V.
    
3. Importe el nuevo certificado AudioVideoAuthentication al servidor perimetral y a todos los demás servidores perimetrales de su grupo (si tiene un grupo implementado).
    
4. Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro-EffectiveDate. La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos vigencia del token (de forma predeterminada ocho horas). Esto nos da la ocasión de que el certificado se debe configurar como activo y es la cadena \<\>-EFFECTIVEDATE: "7/22/2015 6:00:00 a.m.". 
    
    > [!IMPORTANT]
    > En el caso de un grupo perimetral, debe tener todos los certificados de AudioVideoAuthentication implementados y aprovisionados por la fecha y la hora definida por el parámetro-EffectiveDate del primer certificado implementado para evitar posibles interrupciones en las comunicaciones a/V debido al vencimiento del certificado más antiguo antes de que todos los tokens de cliente y consumidor se hayan renovado con el nuevo certificado. 
  
    El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Un ejemplo del comando set-CsCertificate:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor. El ejemplo usa la región de inglés norteamericano y la configuración de idioma 
  
Para obtener más información sobre el proceso que establece-CsCertificate,-roll y-EffectiveDate usar para ensayar un nuevo certificado para emitir nuevos tokens de AudioVideoAuthentication y seguir usando un certificado existente para validar AudioVideoAuthentication que se están usando por los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso. En el siguiente ejemplo, el administrador determina que el certificado de servicio perimetral A/V debe expirar a los 2:00:00 PM en 07/22/2015. Solicita y recibe un nuevo certificado y lo importa a cada servidor perimetral de su grupo. A la 2 de la 07/22/2015, comienza a ejecutar Get-CsCertificate with-roll,-Thumbprint es igual a la cadena de la huella digital del nuevo certificado y-EffectiveTime se establece en 07/22/2015 6:00:00 AM. Este comando se ejecuta en cada servidor perimetral.
  
![Usar los parámetros Roll y EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Globo**|**Fase**|
|:-----|:-----|
|1  <br/> |Inicio: 7/22/2015 12:00:00 A.M.  <br/> El certificado de AudioVideoAuthentication actual se debe a que vence el 2:00:00 PM en 7/22/2015. Esto viene determinado por la marca de tiempo de expiración del certificado. Planee la sustitución y el rollover de su certificado para tener en cuenta una superposición de 8 horas (la duración del token predeterminada) antes de que el certificado existente llegue a la fecha de vencimiento. En este ejemplo, se usa el tiempo de adelanto de 2:00:00, para permitir al administrador el tiempo adecuado para realizar y aprovisionar los certificados nuevos de antemano de la 6:00:00 AM tiempo efectivo.  <br/> |
|1  <br/> |7/22/2015 2:00:00 AM-7/22/2015 5:59:59 AM  <br/> Establecer certificados en servidores perimetrales con un tiempo de vigencia de 6:00:00 AM (el tiempo de entrega de 4 horas es para este ejemplo, pero puede ser más largo \<) mediante el\> tipo de \<uso de certificado-\> huella dactilar de tipo \<Set-CsCertificate (huella dactilar de huella digital de certificado-EffectiveDate DateTime de la hora efectiva para el nuevo certificado\>  <br/> |
|3  <br/> |7/22/2015 6:00 A.M.-7/22/2015 2:00 P.M.  <br/> Para validar los tokens, primero se prueba el certificado nuevo y, si el certificado nuevo no puede validar el token, se intenta el certificado anterior. Este proceso se usa para todos los tokens durante el período de solapamiento de 8 horas (el ciclo de vida de token predeterminado).  <br/> |
|4  <br/> |Fin: 7/22/2015 2:00:01 P.M.  <br/> El certificado antiguo ha expirado y el nuevo certificado ha sido recibido. El certificado antiguo se puede quitar de forma segura con el tipo \<de uso de certificado para quitar-CsCertificate-tipo-anterior\>  <br/> |
   
Cuando se alcance el tiempo de vigencia (7/22/2015 6:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos. Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado. Si se produce un error en la validación, se intenta el certificado anterior. El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior. Una vez que el certificado antiguo haya expirado (7/22/2015 2:00:00 PM), los tokens solo se validarán con el nuevo certificado. El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de OAuthTokenIssuer con parámetros "roll" y "EffectiveDate"

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicite una renovación o un nuevo certificado de OAuthTokenIssuer con una clave privada exportable para el certificado existente en el servidor front-end.
    
3. Importe el nuevo certificado OAuthTokenIssuer a un servidor front-end de su grupo (si tiene un grupo implementado). El certificado OAuthTokenIssuer se replica de forma global y solo es necesario actualizarlo y renovarlo en cualquier servidor de la implementación. El servidor front-end se usa como ejemplo.
    
4. Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro-EffectiveDate. La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos un mínimo de 24 horas. 
    
    El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Un ejemplo del comando set-CsCertificate:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor. El ejemplo usa la región de inglés norteamericano y la configuración de idioma 
  
Cuando se alcance el tiempo de vigencia (7/21/2015 1:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos. Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado. Si se produce un error en la validación, se intenta el certificado anterior. El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior. Una vez que el certificado antiguo haya expirado (7/22/2015 2:00:00 PM), los tokens solo se validarán con el nuevo certificado. El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vea también

[Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Skype empresarial Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
