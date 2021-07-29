# test-wireguard-connectivity


Install Wireguard on each of your Ubuntu nodes:
```
sudo apt install wireguard
```

Enable WireGuard encryption across all the nodes using the following command:
```
kubectl patch felixconfiguration default --type='merge' -p '{"spec":{"wireguardEnabled":true}}'
```

Verify that the nodes are configured for WireGuard encryption:
```
kubectl get node ip-10-0-1-157 -o yaml
```

To test that it’s working you can use wireguard-tools:
```
sudo wg show
```

