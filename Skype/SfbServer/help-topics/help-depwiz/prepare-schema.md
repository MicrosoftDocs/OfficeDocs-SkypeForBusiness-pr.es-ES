---
título: "Preparar esquema" ms.author: jambirk autor: Administrador de jambirk: serdars ms.date: ms.audience 8/2/2018: ms.topic de ITPro: artículo f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep ms.prod: localization_priority de Skype para negocios itpro: Normal ms.assetid: descripción de 337aa234-c5f3-4468-a047-2023848e942c: "para preparar el esquema de servicios de dominio de Active Directory, ejecutar el esquema de preparación paso en el Skype para el Asistente para implementación de Business Server. Haga clic en ejecutar para comenzar la preparación del esquema. El paso Preparar esquema lee los archivos de definición de esquema suministrados que se ubican en el directorio \Archivos de programa\Microsoft Lync Server 2013\Deployment\Setup en el sistema en el que se ejecuta el Asistente para la implementación. Estos archivos también están disponibles en el directorio \Support\Schema del medio de instalación. El paso Preparar esquema ampliará el esquema e informará sobre el estado del proceso. Además, avisará cuando el proceso haya finalizado. En la pantalla de resumen se podrán ver los registros del proceso. Revise los registros para asegurarse de que la preparación sea completa y correcta."
---

# <a name="prepare-schema"></a>Preparar esquema
 
Para preparar el esquema de servicios de dominio de Active Directory, ejecute el paso Preparar el esquema en el Skype para el Asistente para implementación de Business Server. Haga clic en **Ejecutar** para comenzar la preparación del esquema. El paso Preparar esquema lee los archivos de definición de esquema suministrados que se ubican en el directorio \Archivos de programa\Microsoft Lync Server 2013\Deployment\Setup en el sistema en el que se ejecuta el Asistente para la implementación. Estos archivos también están disponibles en el directorio \Support\Schema del medio de instalación. El paso Preparar esquema ampliará el esquema e informará sobre el estado del proceso. Además, avisará cuando el proceso haya finalizado. En la pantalla de resumen se podrán ver los registros del proceso. Examine los registros para asegurarse de que la preparación se haya completado correctamente.
  
> [!IMPORTANT]
> Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización. 
  
Las clases y los atributos se agregan para extender el esquema de servicios de dominio de Active Directory para admitir Skype para server Business Server 2015, servicios y objetos de usuario. Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema. Para obtener información detallada sobre el proceso de copia de seguridad de Windows Server 2008 R2 con SP1, consulte [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Para Windows Server 2003 y Windows Server 2003 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> La ampliación del esquema es una acción que no puede deshacerse. Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta. Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor. Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory. 
  
Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:
  
1. Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.
    
2. Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.
    
3. Amplíe el esquema.
    
4. Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.
    
5. En el improbable caso de un fallo de extensión de esquema, restaure el estado de los sistemas del controlador de dominio y Active Directory utilizando la copia de seguridad de estado del sistema que realizó anteriormente.
    
> [!NOTE]
> Si necesita revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrar los archivos en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios de usuario de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

