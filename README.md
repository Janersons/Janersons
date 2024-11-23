using Photon.Pun;

public class MultiplayerManager : MonoBehaviourPunCallbacks
{
    void Start()
    {
        // Conecta ao servidor Photon
        PhotonNetwork.ConnectUsingSettings();
    }

    public override void OnConnectedToMaster()
    {
        Debug.Log("Conectado ao servidor Photon!");
        PhotonNetwork.JoinLobby(); // Entra no lobby principal
    }

    public override void OnJoinedLobby()
    {
        Debug.Log("Entrou no lobby!");
    }

    public void CreateRoom(string roomName)
    {
        PhotonNetwork.CreateRoom(roomName);
    }

    public void JoinRoom(string roomName)
    {
        PhotonNetwork.JoinRoom(roomName);
    }
}
