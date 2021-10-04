
# Instalar BSPWN y POLYBAR
```
sudo apt-get install bspwm polybar suckless-tools
```
### Crear directorios
```
mkdir ~/.config/bspwm
mkdir ~/.config/sxhkd
mkdir ~/.config/polybar
```
### Copiar archivos de configuracion
```
cp /usr/share/doc/bspwm/examples/bspwmrc ~/.config/bspwm/
cp /usr/share/doc/bspwm/examples/sxhkdrc ~/.config/sxhkd/
cp /usr/share/doc/polybar/config ~/.config/polybar/
```
### Editar archivo
```
gedit ~/.config/sxhkd/sxhkdrc
```
### Añadir terminal funcional
```
gnome-terminal
```
### Crear archivo script
```
gedit ~/.config/polybar/launch.sh
```
### Crear archivo launch.sh
```
#!/usr/bin/env bash

# Terminate already running bar instances
killall -q polybar
# If all your bars have ipc enabled, you can also use
# polybar-msg cmd quit

# Launch bar1 and bar2
echo "---" | tee -a /tmp/polybar1.log /tmp/polybar2.log
polybar example >>/tmp/polybar1.log 2>&1 & disown

echo "Bars launched..."
```
### Dar permisos archvio
```
chmod +x ~/.config/polybar/launch.sh
```
### Editar archivo
```
gedit ~/.config/bspwm/bspwmrc
```
### Añadir al principio
```
$HOME/.config/polybar/launch.sh
```
### Teclas de acceso directo
```
Super + enter 	Abre la terminal
Super + espacio 	Abre el menú (dmenu)
Super + ESC 	Carga la configuración de sxhkd de nuevo
Super + alt + q 	Para salir de BSPWM
Super + alt + r 	Para reiniciar BSPWM
```