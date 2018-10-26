---
title: "Lync Server 2013: Configurar la compatibilidad con dominios externos bloqueados"
TOCTitle: Configurar la compatibilidad con dominios externos bloqueados
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49115285
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Si ha configurado la compatibilidad para socios federados, puede administrar los dominios que se bloquearán de la federación con su organización. La lista de dominios bloqueados actuará como una lista de bloqueo (lista de entradas explícitas que no se van a permitir) y se aplicará en la detección de dominios federados, si tiene activada esta opción. Para más información, vea [Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquee uno o más dominios externos para que no puedan conectarse a su organización. Para hacerlo, agregue el dominio a la lista de dominios bloqueados.

## Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**.

4.  Seleccione **Dominios federados**, haga clic en **Nuevo** y, a continuación, seleccione **Dominio bloqueado**.

5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **Nombre de dominio (o FQDN)**, escriba el nombre de dominio de socio federado que desea bloquear.
        

        > [!NOTE]
        > El nombre no puede superar los 256 caracteres.<BR>La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe <STRONG>contoso.com</STRONG> , la búsqueda devolverá el dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio de socio federado no puede bloquearse y permitirse simultáneamente. Lync Server 2013 impide que esto ocurra para que no tenga que sincronizar las listas.

    
      - (Opcional) En **Comentario**, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.

7.  Repita los pasos del 4 al 6 para cada socio federado que desee bloquear.

Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización. Para más información, vea [Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados. Para más información, vea [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

