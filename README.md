# Markdown
# Heading 1
# Heading 2
# Heading 3
# Heading 4
# Heading 5
# Heading 6

## Lists

- item 1
- item 2
- item 3
* Dot
* More dots
1. Number 1
1. Number 2
1. Number 3

### Split for new list

1. New list
1. Second
1. Third

#### Codeblock

...
    public int Health 
    { 
        get
        {
            return health;
        }
        set
        {
            damageTaken += value;
            health = value;
            foreach(Action<int> action in damageActions)
            {
                action(value);
            }
            if (health <= 0)
            {
                int particles = 5 + Mathf.FloorToInt(rb.velocity.magnitude) * 2;
                float lerpMultiplier = Mathf.LerpUnclamped(0f, 1f, rb.velocity.magnitude / magnitudeUpperLimit);
                deathFX.Play(this, particles, lerpMultiplier);
                foreach (Action action in deathActions)
                {
                    action();
                }

                Reset();
            }
        }
    }
...