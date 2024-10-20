# AulesCSSmod
Modifica la apariencia de Aules (Moodle) usando la extensión "User JavaScript and CSS" en Chrome. Esta extensión permite modificar el código JavaScript y CSS de una página web en el momento de la carga.

En su última actualización (septiembre 2024), Aules ha modificado su aspecto con resultados discutibles. El principal problema, en mi opinión, es que se desperdicia mucho espacio en elementos fijos y en areas vacias, reduciendo el espacio disponible para visualizar y editar información.

Modificaciones que se han implementado:

- Desbloquear la cabecera. Ahora se mueve con el resto de la página.
- Reducir la algura de la cabecera.
- Eliminar la caja de busqueda (no sirve para nada).
- Mover iconos de redes sociales al pie de página.
- Recolocar los bloques laterales.
- Reducir tamaño de los iconos y las fuentes de títulos en las actividades y recursos.
- Los bloques de secciones ocupan el 100% del ancho disponible.
- Las ventanas de areas de texto, editores de texto y explorador de archivos ocupan el 100% del ancho disponible.
- Los enlaces se destacan en color para hacerlos visibles.

## Descargo de responsabilidad
> [!CAUTION]
> Mis conocimientos de CSS están absolutamente desactualizados y las modificaciones descritas se han hecho por el método de prueba-error. Cualquier responsabilidad por el uso de estas modificaciones será del usuario que las aplique.

## Instalación
1. Instala en Chrome la extensión [User JavaScript and CSS](https://chromewebstore.google.com/detail/user-javascript-and-css/nbhcbdghjpllgmfilhnhkllmkecfmpld)
2. Activa el *Modo Desarrollador* para las extensiones de Chrome. En Chrome ve a *Opciones > Extensiones > Gestionar Extensiones*, en la esquina superior derecha encontrarás el botón para activar el *Modo Desarrollador*.
3. Accede a tu aula virtual en Aules y activa la extensión *User JavaScript and CSS* en el menú de extensiones de Chrome.
4. En el desplegable pulsa el botón *New rule*. Se abrirá la página de la extensión. En el campo *URL pattern* aparecerá el texto _https://aules.edu.gva.es/*_ (incluido el asterisco). 
5. Copia el contenido del archivo [CSS](CSS) y pégalo en la columna derecha de la extensión, donde dice *Start typing SCSS or CSS here*.
7. Pulsa el botón *Save*.
8. Recarga la página de tu aula virtual. Las modificaciones se verán inmediatamente.

## Desactivar las modificaciones y desinstalar
Si quieres volver a la versión original de Aules, accede a tu aula virtual y pulsa el icono de la extensión *User JavaScript and CSS* en el menú de extensiones de Chrome. Se desplegará un menú donde podrás desactivar las reglas que hayas definido. Más tarde podrás volver a activar las modificaciones en el mismo sitio.

Si quieres desinstalar definitivamente las modificaciones, puedes eliminar la extensión desde *Gestionar extensiónes* de Chrome. También es posible eliminar una regla individual la extensión sin desinstalarla.

## Cambiar el color de los enlaces en Aules
Por defecto, en Aules **no** se destacan los enlaces de ninguna forma, lo cual dificulta la usabilidad y genera barreras de accesibilidad.

En las modificaciones se han configurado los enlaces para que se destaquen en el color **azul** `#0000EE`que usan los navegadores por defecto. Se mostrará este color para todos los sabores de Aules.

Si únicamente utilizas un sabor de Aules y quieres el color de los enlaces a juego con tu sabor, puedes cambiarlo en el código que has pegado en el paso 5. El código a modificar esta al final, he dejado algunos colores preparados para que pongas el que quieras. Puedes hacer el cambio en la página de la extensión. El código es este:
```css
a:not([class])  {
  /*Color azul estandar para enlaces*/
  color: #0000ee;
  /*Color para FP Semipresencial*/
  /*color: #AE0046;*/
  /*Color para FP*/
  /*color: #006444;*/
}
```

Si utilizas más de un sabor de Aules y quieres colores de enlaces a juego con cada sabor, tendrás que crear una regla personalizada para cada uno de ellos. 

Por ejemplo: para Aules FP, crea una regla de la misma forma que en el paso 4 de la instalación y modifica el campo *URL pattern* poniendo _https://aules.edu.gva.es/fp/*_ (incluido el asterisco). Fíjate en el añadido de ***fp*** en la URL. Cada sabor de Aules tiene un añadido diferente. En la columna derecha de la extensión, añade el siguiente código CSS:
```css
a:not([class])  {
  /*Color para FP*/
  color: #006444 !important;
}
```

Repite lo anterior para cada sabor de Aules, cambiando el añadido en la URL y el color.
