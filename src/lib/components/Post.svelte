<script lang="ts">
  import Card from '$lib/components/Card.svelte';

  import { humanTimeExpression } from '$lib/utils/datetime';
  import Avatar from './Avatar.svelte';

  import type { PostFragmentFragment } from '$lib/graphql/schema';

  export let post: PostFragmentFragment;
</script>

<Card>
  <header class="flex items-center justify-start">
    <Avatar user={post.user} size="md" />
    <div class="flex flex-col px-2">
      <strong class="text-gray-800">{post.user.username}</strong>
      <span class="text-gray-400 text-sm">{humanTimeExpression(new Date(post.createdAt))}</span>
    </div>
  </header>
  <main class="pt-4">
    <p>{post.content}</p>
  </main>
</Card>
