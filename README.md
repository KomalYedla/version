# version

for plugin in $(gst-inspect-1.0 | awk -F: '{print $1}' | sort -u); do
    echo -n "$plugin: "
    gst-inspect-1.0 --plugin "$plugin" 2>/dev/null | grep Version | head -n 1 | sed 's/^ *Version *//'
done
