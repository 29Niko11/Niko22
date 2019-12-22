
using System.Collections;
using System.Collections.Generic;

using UnityEngine;
using Sprite = UnityEngine.Sprite;

public class Ghost : MonoBehaviour {

    [SerializeField]
    SpriteRenderer Sprite;
    float Timer = 0.2f;
    // Start is called before the first frame update
    void Start()
    {
        Sprite = GetComponent<SpriteRenderer>();
        transform.position = PlayerAL.Instance.transform.position;
        transform.localScale = PlayerAL.Instance.transform.localScale;
        Sprite.sprite = PlayerAL.Instance.PlayerSprite.sprite;
        Sprite.color = new Vector4(50, 50, 50, 0.2f);
    }


    // Update is called once per frame
    void Update()
    {
        Timer -= Time.deltaTime;

        if (Timer <= 0)
            Destroy(gameObject);
    }
}
