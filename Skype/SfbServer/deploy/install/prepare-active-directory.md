---
title: 'Skype Empresarial Server: Preparación de Active Directory'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumen: obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype Empresarial Server.'
ms.openlocfilehash: b40eccab3d2f71e5211a1c67342440a86497023d
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860581"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype Empresarial Server: Preparación de Active Directory
 
**Resumen:** Obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype Empresarial Server.
  
Skype Empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para trabajar con Skype Empresarial Server. Este proceso se realiza en el Asistente para la implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y debe hacerlo solo una vez. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, como se describe en el diagrama. La preparación de Active Directory es el paso 4 del 8. Para obtener más información sobre la planeación de Active Directory, consulte [Requisitos ambientales para Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Requisitos del servidor para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagrama de información general.](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar Active Directory

Skype Empresarial Server está estrechamente integrado con Servicios de dominio de Active Directory (AD DS). Para poder instalar Skype Empresarial Server por primera vez, active directory debe estar preparado. La sección del Asistente para implementación titulada **Preparar Active Directory** prepara el entorno de Active Directory para su uso con Skype Empresarial Server.
  
> [!NOTE]
> Skype Empresarial Server usa (AD DS) para realizar un seguimiento y comunicarse con todos los servidores de una topología. La mayoría de estos servidores deben estar unidos al dominio para que Skype Empresarial Server funcionen correctamente. Tenga en cuenta que los servidores como Edge y Reverse Proxy no deben estar unidos a un dominio.
  
> [!IMPORTANT]
> El procedimiento Preparar Active Directory solo se debe ejecutar una vez para cada dominio de la implementación. 
  
Vea los pasos de vídeo para **preparar Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparación de Active Directory desde el Asistente para implementación

1. Inicie sesión como usuario con credenciales de administradores de esquema para el dominio de Active Directory.
    
2. Abra Skype Empresarial Server Asistente para la implementación.
    
    > [!TIP]
    > Si desea revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación, en el directorio Usuarios del usuario de AD DS que ejecutó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio contoso.local, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Haga clic en el vínculo **Preparar Active Directory** .
    
4. **Paso 1: Preparación del esquema**
    
    a. Revise la información de requisitos previos del paso 1 a la que se puede acceder haciendo clic en la lista desplegable del título Paso 1.
    
    b. Haga clic en **Ejecutar** en el paso 1 para iniciar el Asistente para preparar esquemas.
    
    c. Tenga en cuenta que el procedimiento debe ejecutarse solo una vez para cada implementación y, a continuación, haga clic en **Siguiente**.
    
    d. Una vez preparado el esquema, puede ver el registro haciendo clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** para cerrar el Asistente para preparar el esquema y volver a los pasos preparar Active Directory.
    
5. **Paso 2: Comprobar la replicación de la partición de esquema**
    
    a. Inicie sesión en el controlador de dominio del dominio.
    
    b. Abra **ADSI Edit (Editar ADSI**) en el menú desplegable **Herramientas** de **Administrador del servidor**.
    
    c. En el menú **Acción**, haga clic en **Conectar con**.
    
    d. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, a continuación, haga clic en **Aceptar**.
    
    e. En el contenedor de esquema, busque **CN=ms-RTC-SIP-SchemaVersion**. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se actualizó y replicó correctamente. Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** no son los especificados, el esquema no se modificó o no se ha replicado.
    
6. **Paso 3: Preparación del bosque actual**
    
    a. Revise la información de requisitos previos del paso 3 a la que se puede acceder haciendo clic en la lista desplegable bajo el título Paso 3.
    
    b. Haga clic en **Ejecutar** en el paso 3 para iniciar el Asistente para preparar el bosque actual.
    
    c. Tenga en cuenta que el procedimiento solo se debe ejecutar una vez por implementación y, a continuación, haga clic en **Siguiente**.
    
    d. Especifique el dominio donde se crearán los grupos universales. Si el servidor forma parte del dominio, puede elegir **Dominio local** y hacer clic en **Siguiente**.
    
    e. Una vez preparado el bosque, puede ver el registro haciendo clic en **Ver registro**. 
    
    f. Haga clic en **Finalizar** para cerrar el Asistente para preparar el bosque actual y volver a los pasos preparar Active Directory.
    
    g. Haga clic en **Skype Empresarial Server Shell de administración** en la página **Aplicaciones** para iniciar PowerShell.
    
    h. Escriba el comando Get-CsAdForest y presione **Entrar**.
    
    i. Si el resultado se **LC_FORESTSETTINGS_STATE_READY**, el bosque se ha preparado correctamente, como se muestra en la ilustración.
    
     ![Compruebe la replicación del bosque.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Paso 4: Comprobar la replicación del catálogo global**
    
    a. En un controlador de dominio (preferiblemente en un sitio remoto desde otros controladores de dominio) del bosque en el que se ejecutó la preparación del bosque, abra  **Usuarios y equipos de Active Directory**.
    
    b. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
    c. Haga clic en el contenedor **Usuarios** en el panel izquierdo y busque el grupo universal **CsAdministrator** en el panel derecho. Si CsAdministrator (entre otros nuevos grupos universales que comienzan por Cs) está presente, la replicación de Active Directory se ha realizado correctamente.
    
    d. Si los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
8. **Paso 5: Preparación del dominio actual**
    
    a. Revise la información de requisitos previos del paso 5.
    
    b. Haga clic en **Ejecutar** en el paso 5 para iniciar el Asistente para preparar el dominio actual.
    
    c. Tenga en cuenta que el procedimiento solo debe ejecutarse una vez para cada dominio de la implementación y, a continuación, haga clic en **Siguiente**.
    
    d. Una vez preparado el dominio, puede ver el registro haciendo clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** para cerrar el Asistente para preparar el dominio actual y volver a los pasos De preparación de Active Directory.
    
    Estos pasos deben completarse en todos los dominios en los que se encuentran Skype Empresarial Server objetos; de lo contrario, es posible que los servicios no se inicien. Esto incluye cualquier tipo de objeto de Active Directory, como usuarios, objetos de contacto, grupos administrativos o cualquier otro tipo de objeto. Puede usar Set-CsUserReplicatorConfiguration -ADDomainNamingContextList para agregar solo los dominios con objetos Skype Empresarial Server, si es necesario.
    
9. **Paso 6: Comprobar la replicación en el dominio**
    
    a. Haga clic en el **shell de administración de Skype Empresarial Server** en la página **Aplicaciones** para iniciar PowerShell.
    
    b. Use el comando Get-CsAdDomain para comprobar la replicación dentro del dominio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Si no especifica el parámetro de dominio, el valor se configura con el dominio local. 
  
    Ejemplo de ejecución del comando para el dominio contoso.local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Mediante el parámetro GlobalSettingsDomainController, puede indicar dónde se almacena la configuración global. Si la configuración se almacena en el contenedor del sistema (lo que es habitual con las implementaciones de actualización que no han migrado la configuración global al contenedor de configuración), defina un controlador de dominio en la raíz del bosque de AD DS. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet supone que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    c. Si el resultado se **LC_DOMAINSETTINGS_STATE_READY**, el dominio se ha replicado correctamente.
    
10. **Paso 7: Agregar usuarios para proporcionar acceso administrativo a la Skype Empresarial Server Panel de control**
    
    a. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic en el contenedor **Usuarios**, haga clic con el botón derecho en CSAdministrator y elija **Propiedades**.
    
    c. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
    d. En la pestaña **Miembros**, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
    e. En la pestaña **Miembros** , confirme que están presentes los usuarios o grupos seleccionados. Haga clic en **Aceptar**.
    
    > [!CAUTION]
    > El Skype Empresarial Server Panel de control es una herramienta de control de acceso basada en rol. La pertenencia al grupo CsAdministrator proporciona a un usuario que usa el Skype Empresarial Server Panel de control control total para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Para obtener más información sobre los roles disponibles, consulte [Requisitos del entorno para los requisitos de Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [servidor para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md). Tenga en cuenta que los usuarios no tienen que estar habilitados para Skype Empresarial Server para ser miembros de los grupos de administración. 
  
    > [!CAUTION]
    > Para ayudar a conservar la seguridad y la integridad del control de acceso basado en rol, agregue usuarios a los grupos que definen qué rol desempeña el usuario en la administración de la implementación de Skype Empresarial Server. 
  
11. Cierre la sesión y vuelva a iniciar sesión en Windows para que el token de seguridad se actualice con el nuevo grupo de seguridad Skype Empresarial Server y vuelva a abrir el Asistente para la implementación.
    
12. Compruebe que ve una marca de verificación verde junto a **Preparar Active Directory** para confirmar que se ha realizado correctamente, como se muestra en la ilustración.
    
     ![Preparar Active Directory completado.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Vea también
 
[Servicios de dominio de Active Directory para Skype Empresarial Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
